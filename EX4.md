# Ex.No:4

# Ex.Name: Write A C++ Graph implementation using STL for competitive programming | (DFS of Unweighted and Undirected)


## Date:

## Aim:
To implement a Depth-First Search (DFS) traversal of an unweighted, undirected graph using STL vectors in C++ for competitive programming.

## Algorithm:
STEP 1: Start the program.

STEP 2: Define a graph using vector adj[n] for adjacency lists.

STEP 3: Define a boolean vector visited[n] to track visited vertices.

STEP 4: Define a function addEdge(vector adj[], int u, int v) to add an edge:

adj[u].push_back(v)

adj[v].push_back(u) (undirected graph)

STEP 5: Define a recursive DFS function DFS(vector adj[], int v, vector &vis) that:

Marks v as visited: vis[v] = true

Prints vertex v

Recursively visits all unvisited neighbors of v

STEP 6: In main(), read number of vertices n.

STEP 7: Initialize adjacency list adj[n] and visited[n].

STEP 8: Read edges (pairs of vertices) and call addEdge() for each edge.

STEP 9: Call DFS(adj, start_vertex, visited) to perform DFS from a starting vertex.

STEP 10: End the program.




## Program:
```
#include <bits/stdc++.h>
using namespace std;
void addEdge(vector<int> adj[], int u, int v)
{
    adj[u].push_back(v);
}

void DFS(vector<int> adj[], int v, vector<bool> &vis)
{
    vis[v] = true;
    cout<<v<<" ";
    for(auto i :adj[v])
    {
        if(vis[i] == false)
        {
            DFS(adj, i , vis);
        }
    }
}

int main()
{ 
    int n ,a,b;
    cin>>n;
    vector<int>adj[n];
    vector<bool>visited(n,false);
    for(int i = 0 ;i < n ;i++)
    {
        cin>>a>>b;
        addEdge(adj,a,b);
    }
    DFS(adj, 1, visited);
}
```


## Output:

<img width="702" height="768" alt="519163722-bf5a908e-fc59-49c6-981d-e9260187271e" src="https://github.com/user-attachments/assets/b6f93bfe-98ff-49e5-a10e-d2b9eafa89c5" />


 ## Result:
The program prints the DFS traversal of an unweighted, undirected graph.

