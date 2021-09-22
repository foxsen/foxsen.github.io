---
title: set excerpt type to html
tags: TeXt
cover: /docs/assets/images/axure/page-aside.jpg
aside:
  toc: true
---

TeXt theme can show blog excerpts as text or html. The default _config.yml does not set the variable and defaults to text. 
So all new lines are missing for the home page.

Set articles.excerpt_type for home page to html will solve it.

<!--more-->

See the following patch.

```
@@ -200,8 +200,16 @@ exclude:
   - /screenshots
   - /test
   - /vendor
+  - /tools

 defaults:
+  ## home
+  - scope:
+      path: ""
+    values:
+      articles:
+        excerpt_type: html
+  ## posts
   - scope:
       path: ""
       type: posts
```
