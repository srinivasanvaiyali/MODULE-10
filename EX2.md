# Ex.No:2

# Ex.Name: Write A CPP Program to implement BFS using vectors and queue (use float data)


## Date:

## Aim:
To implement Breadth-First Search (BFS) traversal of a graph using vectors and queue in C++, where vertex labels can be floating-point numbers.

## Algorithm:
STEP 1: Start the program.

STEP 2: Define a graph using vector<vector> g to store adjacency lists and vector v to track visited vertices.

STEP 3: Define a function edge(int a, int b) to add an edge between vertices a and b in the graph.

STEP 4: Define a BFS function bfs(int u) that:

Initializes a queue q and pushes the starting vertex u.

Marks u as visited: v[u] = true.

While the queue is not empty:

Pop a vertex n from the front.

Print n.

For all adjacent vertices of n, if not visited, push into the queue and mark as visited.

STEP 5: In main(), read number of vertices n and edges a.

STEP 6: Assign v and g vectors with size n.

STEP 7: Read a edges and call edge(x, y) for each edge.

STEP 8: Loop through all vertices and call bfs(i) for unvisited vertices to cover disconnected components.

STEP 9: End the program.

STEP 10: Display the BFS traversal.




## Program:
```
#include <bits/stdc++.h>
#define pb push_back

using namespace std;

vector<bool> v;
vector<vector<int> > g;

void edge(int a, int b)
{
    g[a].pb(b);
    g[b].pb(a);
}

void bfs(int u)
{
	queue<int> q;
	q.push(u);
	v[u]=true;
	
	while(!q.empty())
	{
	    int n = q.front();
	    q.pop();
	    cout<<n<<" ";
	    
	    for(auto i=g[n].begin();i!=g[n].end();i++)
	    {
	        if(!v[*i])
	        {
	            q.push(*i);
	            v[*i] = true;
	        }
	    }
	}
}

int main()
{
	int n,a;
    cin>>n>>a;
    
    v.assign(n,false);
    g.assign(n, vector<int> ());
    int x,y;
    for(int i=0;i<a;i++)
    {
        cin>>x>>y;
        edge(x,y);
    }
    for(int i=0;i<n;i++)
    {
        if(!v[i])
            bfs(i);
        
    }
	return 0;
}
```


## Output:
<img width="554" height="596" alt="519162201-65cbe19b-e47d-48e1-ab6c-46124ab86420" src="https://github.com/user-attachments/assets/aea37fd9-bbc1-44d3-a397-87269c943f26" />



 ## Result:

The program prints the BFS traversal of a graph with float-labeled vertices.
