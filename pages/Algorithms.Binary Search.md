title:: Algorithms/Binary Search
alias:: 算法/二分查找

- 给定一个有序的数组，查找 target 是否在数组中，不存在返回 -1。
- ```go
  type value interface {
  	int | string
  }
  
  func binarySearch[val value](array []val, target val) int {
  	start := 0
  	end := len(array) - 1
  	for start <= end {
  		mid := (start + end) / 2
  		if array[mid] == target {
  			return mid
  		} else if array[mid] < target {
  			start = mid + 1
  		} else if array[mid] > target {
  			end = mid - 1
  		}
  	}
  	return -1
  }
  ```