- # 日志
- #+BEGIN_QUERY
  {:title "week day"
  :query [:find ?title
  :where
  [:block/journal-day ?title]]}
  #+END_QUERY
-
-
-
-
-
- # 快捷方式
- [:a {:href "#/all-journals"} "所有日记"]
- [:a {:href "https://www.ganymedenil.com"} "我的博客"]
- [[关于我]]