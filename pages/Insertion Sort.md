alias:: 插入排序

- ```go
  func InsertionSort(inputs []int) {
  	for i := 1; i < len(inputs); i++ {
  		key := inputs[i]
  		last := i - 1
  		for last >= 0 && key < inputs[last] {
  			inputs[last+1] = inputs[last]
  			last = last - 1
  		}
  		inputs[last+1] = key
  	}
  }
  ```
- 计算复杂度 O(n^2)
- 空间复杂度O(1)