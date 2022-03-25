alias:: 冒泡排序

- ```go
  func BubbleSort(inputs []int) {
  	for i := 0; i < len(inputs); i++ {
  		for j := 0; j < len(inputs)-1-i; j++ {
  			if inputs[j] > inputs[j+1] {
  				inputs[j], inputs[j+1] = inputs[j+1], inputs[j]
  			}
  		}
  	}
  	return
  }
  ```
- 时间复杂度 O(n^2)
- 空间复杂度O(1)