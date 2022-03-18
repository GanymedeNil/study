- # 日志
- #+BEGIN_QUERY
  {:title "week day"
  :query [:find (pull ?b [*])
  :where
  [?b :block/journals]
  ]
  }
  #+END_QUERY
-
-
-
- # 快捷方式
- [:a {:href "#/all-journals"} "所有日记"]
- [:a {:href "https://www.ganymedenil.com"} "我的博客"]
- [[关于我]]