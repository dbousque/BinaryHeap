# BinaryHeap
A simple to use and fast binary heap implementation in Java.

The heap is meant to be used as a priority queue.

You can construct the heap like so :
```
BinaryHeap heap = new BinaryHeap();

// You can also specify whether the heap has the object with the highest or the lowest value on top :
BinaryHeap heap = new BinaryHeap(BinaryHeap.MAX);
BinaryHeap heap = new BinaryHeap(BinaryHeap.MIN);
// Default is BinaryHeap.MAX
```

The API is very simple, the following functions are available :
  - ```add(Object o)``` : adds your object to the heap
  - ```pop()``` : removes and returns the object currently at the top of the heap
  - ```getTop()``` : returns (but doesn't remove) the object on the top
  - ```size()``` : number of objects on the heap
  - ```isEmpty()```

The objects put on the heap must be Comparable :
```
public class SearchNode implements Comparable<SearchNode>
{

  public int priority;
  
  public SearchNode(int priority)
  {
    this.priority = priority;
  }
  
  public int compareTo(SearchNode otherNode)
  {
    return (this.priority - otherNode.priority);
  }

}
```
Here is a complete example using the SearchNode class:
```
BinaryHeap heap = new BinaryHeap();
for (int i = 1; i <= 5; i++)
{
  heap.add(new SearchNode(i));
}
while (!heap.isEmpty())
{
  SearchNode topNode = (SearchNode)heap.pop();
  System.out.println(topNode.priority);
}
// The output will be : 5, 4, 3, 2, 1
```
