- # 日志
- query-table:: false
  #+BEGIN_QUERY
  {:title "Blocks in 7ds with a page reference of datalog"
   :query [:find (pull ?d[*])
         :in $ ?start ?today
         :where
         [?b :page/journal-day ?d]
         [(>= ?d ?start)]
         [(<= ?d ?today)]]
   :inputs [:7d-before :today]}
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