- # 日志
- #+BEGIN_QUERY
  {:title "Blocks in 7ds with a page reference of datalog"
   :query [:find (pull ?b [*])
         :in $ ?start ?today ?tag
         :where
         [?b :page/journal-day ?d]
         [(>= ?d ?start)]
         [(<= ?d ?today)]
         [?b :block/ref-pages ?rp]
         [?rp :block/name ?tag]]
   :inputs [:7d-before :today "datalog"]}
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