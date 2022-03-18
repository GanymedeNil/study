- # 日志
- {{function #+BEGIN_QUERY
  {:title "All tasks"
   :query [:find (pull ?b [*])
         :where
         [?b :block/marker ?m]
         [(not= ?m "nil")]]}
  #+END_QUERY}}
-
- # 快捷方式
- [:a {:href "#/all-journals"} "所有日记"]
- [:a {:href "https://www.ganymedenil.com"} "我的博客"]
- [[关于我]]