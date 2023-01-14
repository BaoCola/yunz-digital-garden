---
{"dg-publish":true,"permalink":"/02.Blog/coding/gradle切换maven-publish插件的依赖传递问题/","tags":["coding","gradle","mavem-publish"]}
---


<< [[01.Guide/coding\|coding]] | [[03.Diary/2023-01-10_Tue\|2023-01-10_Tue]]

> It requires wisdom to understand wisdom: the music is nothing if the audience is deaf.  
> — <cite>Walter Lippmann</cite>

![photo by Cem Sagisman on Unsplash](https://images.unsplash.com/photo-1590074921935-71b32ae91b30?crop=entropy&cs=tinysrgb&fm=jpg&ixid=MnwzNjM5Nzd8MHwxfHJhbmRvbXx8fHx8fHx8fDE2NzMzNjQyMDc&ixlib=rb-4.0.3&q=80&w=200&h=200)

最近 sdk 项目 gradle 版本升级，maven 插件不再支持，需要切换到 maven-publish。但切换完后业务侧报错，sdk 的依赖没有传递过去。

研究了一下，发现几个问题：
- maven 插件默认传递依赖，maven-publish 默认不传递依赖；
- maven 插件生成的 pom 文件中依赖 scope 默认为 compile，而 maven-publish 插件配置依赖传递后会依据一定规则设置 scope；

## 依赖传递

参考博客 [^1] 与官方 wiki[^2]，maven-publish 插件需要进行如下配置，才可以传递依赖。

```groovy
afterEvaluate {
	publishing {
		publications {
			maven(MavenPublication) {
				from components.release // here
				
				groupId = 'com.example.MyLibrary'
				artifactId = 'final'                
				version = '1.0'            
			}
		}
	}
	
	repositories {
		maven {
			name = 'myrepo'
			url = "${project.buildDir}/repo"
		}
	}
}
```

## scope

maven-publish 插件对生成 pom 文件中依赖的 scope 设置了一定的规则：
- implementation 依赖对应的 scope 为 runtime；
- api 依赖对应的 scope 为 compile；

## 安卓的依赖传递

这里简单理解一下安卓的依赖传递机制 [^3]： 

```ad-info
implementation：Gradle 会将依赖项添加到编译类路径，并将依赖项打包到构建输出。不过，当您的模块配置 implementation 依赖项时，会让 Gradle 了解您不希望该模块在编译时将该依赖项泄露给其他模块。也就是说，其他模块只有在运行时才能使用该依赖项。

api：Gradle 会将依赖项添加到编译类路径和构建输出。当一个模块包含 api 依赖项时，会让 Gradle 了解该模块要以传递方式将该依赖项导出到其他模块，以便这些模块在运行时和编译时都可以使用该依赖项。
```

APK A 依赖 SDK S，SDK 依赖第三方软件 T，SDK 软件发布时三方依赖不会被打包到 aar 包中（fat-aar 可以将依赖直接打到包里），只是会将需要的依赖信息写入到关联的 pom 文件发布。APK 在依赖 SDK 时会使用 pom 文件下载相关依赖，发布最终的安装包。

结合上面所述的 maven-publish 生成 pom 文件 scope 的规则，implementation 对应 scope 为 runtime，自然无法被 APK 编译时所使用，而 api 对应 scope 为 compile，编译和运行时均可以被使用。

[^1]: https://juejin.cn/post/7017608469901475847
[^2]: https://developer.android.com/studio/build/maven-publish-plugin?hl=zh-cn
[^3]: https://developer.android.com/studio/build/dependencies?hl=zh-cn
