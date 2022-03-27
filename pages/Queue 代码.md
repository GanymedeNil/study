- ```go
  package main
  
  import (
  	"errors"
  )
  
  
  type Queue[T any] struct {
  	Items []any
  }
  
  func NewQueue[T any]() *Queue[T] {
  	return &Queue[T]{}
  }
  
  func (q *Queue[T]) Enqueue(item T) {
  	q.Items = append(q.Items, item)
  }
  
  func (q *Queue[T]) Dequeue() (*T, error) {
  	defer func() {
  		q.Items = q.Items[1:]
  	}()
  	if len(q.Items) > 0 {
  		item := q.Items[0].(T)
  		return &item, nil
  	}
  	return nil, errors.New("no data")
  }
  func (q *Queue[T]) Peek() (*T, error) {
  	if len(q.Items) > 0 {
  		item := q.Items[0].(T)
  		return &item, nil
  	}
  	return nil, errors.New("no data")
  }
  
  func (q *Queue[T]) Len() int {
  	return len(q.Items)
  }
  
  func QueueInt() {
  	w := tabwriter.NewWriter(os.Stdout, 15, 0, 1, ' ', tabwriter.Debug)
  	fmt.Fprintln(w, "type is int")
  	fmt.Fprintln(w, "func\tvalue\t")
  	q := NewQueue[int]()
  	q.Enqueue(1)
  	q.Enqueue(3)
  	q.Enqueue(10)
  	item, err := q.Dequeue()
  	fmt.Fprintf(w, "dequeue\t%d\t\n", *item)
  	if err != nil {
  		fmt.Println(err)
  	}
  	item, err = q.Peek()
  	fmt.Fprintf(w, "peek\t%d\t\n", *item)
  	if err != nil {
  		fmt.Println(err)
  	}
  	fmt.Fprintf(w, "len\t%d\t\n", q.Len())
  	w.Flush()
  }
  func QueueString() {
  	w := tabwriter.NewWriter(os.Stdout, 15, 0, 1, ' ', tabwriter.Debug)
  	fmt.Fprintln(w, "type is string")
  	fmt.Fprintln(w, "func\tvalue\t")
  	q := NewQueue[string]()
  	q.Enqueue("a")
  	q.Enqueue("b")
  	q.Enqueue("c")
  	item, err := q.Dequeue()
  	fmt.Fprintf(w, "dequeue\t%s\t\n", *item)
  	if err != nil {
  		fmt.Println(err)
  	}
  	item, err = q.Peek()
  	fmt.Fprintf(w, "peek\t%s\t\n", *item)
  	if err != nil {
  		fmt.Println(err)
  	}
  	fmt.Fprintf(w, "len\t%d\t\n", q.Len())
  	w.Flush()
  }
  
  func main() {
  	QueueInt()
  	QueueString()
  }
  ```
- [在线运行](https://go.dev/play/p/jKiHq60zi2S)