---
seo_title: 朋友文章
robots: noindex,nofollow
menu_id: test
comments: false
post_list: true # 这就意味着页面会显示首页文章导航栏
sidebar: [welcome, recent]
---

{% timeline type:fcircle api:https://raw.github.xaoxuu.com/friends-rss/output/data.json %}
{% endtimeline %}