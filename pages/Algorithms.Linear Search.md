title:: Algorithms/Linear Search
alias:: 算法/线性搜索

- ```go
  type value interface {
  	int | string
  }
  
  func lineSearch[val value](array []val, target val) int {
  	for index, item := range array {
  		if item == target {
  			return index
  		}
  	}
  	return -1
  }
  ```
-