---
{"dg-publish":true,"permalink":"/04.Res/template/t-blog/"}
---

<%*
let titleName = tp.file.title
let today = tp.file.creation_date("YYYY-MM-DD_ddd")
let category = await tp.system.prompt("类别", "coding")
let createTime = tp.file.creation_date("YYYY-MM-DD ddd HH:mm:ss")
let updateTime = tp.file.last_modified_date("YYYY-MM-DD ddd HH:mm:ss")
-%>
---
aliases: [<% titleName %>]
category: <% category %>
tags: [<% category %>]
status: init
link: NA
date created : <% createTime %>
date modified: <% updateTime %>
dg-publish: false
---

<< [[01.Guide/<% category %>\|<% category %>]] | [[<% today %>\|<% today %>]]

<% tp.web.daily_quote() %>

<% tp.web.random_picture("200x200", "landscape,water") %>

<%*
await tp.file.move("/02.Blog/" + category + "/" + titleName)
tp.file.cursor()
-%>