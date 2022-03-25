alias:: 归并排序

- ```go
  func MergeSort(inputs []int) []int {
  	if len(inputs) == 1 {
  		return inputs
  	}
  	middle := len(inputs) / 2
  	left := inputs[0:middle]
  	right := inputs[middle:]
  	leftResult := MergeSort(left)
  	rightResult := MergeSort(right)
  
  	return merge(leftResult, rightResult)
  }
  
  func merge(leftResult, rightResult []int) []int {
  	result := make([]int, len(leftResult)+len(rightResult))
  	var i, j, k int
  	for i < len(leftResult) && j < len(rightResult) {
  		if leftResult[i] <= rightResult[j] {
  			result[k] = leftResult[i]
  			i += 1
  		} else {
  			result[k] = rightResult[j]
  			j += 1
  		}
  		k += 1
  	}
  	for i < len(leftResult) {
  		result[k] = leftResult[i]
  		i += 1
  		k += 1
  	}
  	for j < len(rightResult) {
  		result[k] = rightResult[j]
  		j += 1
  		k += 1
  	}
  	return result
  }
  ```
- 计算复杂度O(nlogn)
- 空间复杂度O(n)