alias:: 选择排序

- ```go
  func SelectionSort(inputs []int) {
  	for i := 0; i < len(inputs); i++ {
  		min := i
  		for j := i + 1; j < len(inputs); j++ {
  			if inputs[j] < inputs[min] {
  				min = j
  			}
  		}
  		inputs[i], inputs[min] = inputs[min], inputs[i]
  	}
  }
  ```
- 计算复杂度 O(n^2)
- 空间复杂度O(1)