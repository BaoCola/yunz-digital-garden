---
{"dg-publish":true,"permalink":"/04.Res/template/t-diary/"}
---

<%*
let titleName = tp.file.title
before_date = window.moment(titleName, "YYYY-MM-DD_ddd", true).add(-1,"days").format("YYYY-MM-DD_ddd")
after_date = window.moment(titleName, "YYYY-MM-DD_ddd", true).add(1,"days").format("YYYY-MM-DD_ddd")
let createTime = tp.file.creation_date("YYYY-MM-DD ddd HH:mm:ss")
let updateTime = tp.file.last_modified_date("YYYY-MM-DD ddd HH:mm:ss")
-%>
---
aliases: [<% titleName %>]
category: diary
tags: [diary]
status: init
date created : <% createTime %>
date modified: <% updateTime %>
---

<< [[03.diary/<% before_date %>\|<% before_date %>]] | [[03.Diary/<% after_date %>\|<% after_date %>]] >>

<% tp.web.daily_quote() %>

<% tp.web.random_picture("200x200", "landscape,water") %>

#tasks
<%*
await tp.file.move("/03.Diary/" + titleName)
tp.file.cursor()
-%>