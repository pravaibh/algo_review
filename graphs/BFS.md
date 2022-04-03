This search is a queue based traversal.

Algo:
(INIT phase)
```
a. Modify graph vertex to have color, prev (will be used later to print the path) and dist (from source) on each vertex.
```
```
b. for each vertex u that's not source s,
  i. u.color = WHITE
  ii. u.dist = infinite,
  iii. u.prev = null
```

```
c. Update source vertex as : 
  i. s.color = GREY, 
  ii. s.dist = 0, 
  iii. s.prev = null
```

```
d. Initialize a queue. Add source to it.
```

(TRAVERSAL phase)

```
e. While queue isn't empty,
  i. u = dequeue from queue,
  ii. for each vertex v adjacent to u (check adjacency list of graph)
    - if v.color is WHITE
      v.color set to GREY
      v.d = u.d + 1 (or plus the weight)
      v.prev = u
      enqueue v
  iii. change color of u to BLACK as we visited all the adjacent vertices of u.
```
 To get the shortest path from s to any vertex, break the algo when you first encounter that destination vertex.
 To print the path you can create a recursive fn:
 
```
 printPath(Graph, s , d):
  if d == s, break
  elseif d.prev == null, there is no path,
  else printPath(graph, s, d.prev)
  print d
```
  
