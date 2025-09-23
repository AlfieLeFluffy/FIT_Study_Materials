---
tags:
  - IDM
aliases:
  - depth first search
  - DFS
---
Algorithm first moves into the most distant layer and then gradually goes closer and then deeper into the graph until it searches through all vertexes. As [[Memory|memory]] it uses a [[Stack|stack]].
![[Graphs_Algorithm_DFS.excalidraw.svg]]
## Process
The DFS renders as:
1. Starting vertex is pushed onto the stack.
2. If the stack is not empty then render the top vertex in the stack. Rendering a vertex means checking for target value and then pushing all of  its immediate descendants onto the stack.
