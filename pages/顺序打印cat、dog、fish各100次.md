- ```go
  package main
  
  import (
  	"fmt"
  	"sync"
  )
  
  var wg sync.WaitGroup
  
  func main() {
  	catCh := make(chan bool, 1)
  	dogCh := make(chan bool, 1)
  	fishCh := make(chan bool, 1)
  	catCh <- true
  
  	go printCat(catCh, dogCh)
  	go printDog(dogCh, fishCh)
  	go printFish(fishCh, catCh)
  
  	wg.Add(3)
  	wg.Wait()
  }
  
  func printCat(catCh, dogCh chan bool) {
  	defer wg.Done()
  	defer close(dogCh)
  	for i := 0; i < 100; i++ {
  		<-catCh
  		fmt.Println("cat")
  		dogCh <- true
  
  	}
  }
  func printDog(dogCh, fishCh chan bool) {
  	defer wg.Done()
  	defer close(fishCh)
  	for i := 0; i < 100; i++ {
  		<-dogCh
  		fmt.Println("dog")
  		fishCh <- true
  	}
  }
  func printFish(fishCh, catCh chan bool) {
  	defer wg.Done()
  	defer close(catCh)
  	for i := 0; i < 100; i++ {
  		<-fishCh
  		fmt.Println("fish")
  		catCh <- true
  	}
  }
  ```
- [在线运行](https://go.dev/play/p/lnY9yxlwA9g)