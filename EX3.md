# Ex.No: 3

# Ex.Name: Write A CPP Program to implement BFS using vectors and queue (use character data)

## Date:

## Aim:
To implement Breadth-First Search (BFS) traversal of a graph using vectors and queue in C++, where vertices are characters.

## Algorithm:
STEP 1: Start the program.

STEP 2: Define a graph using vector<vector> g and a vector v to track visited vertices.

STEP 3: Define a map<char,int> to assign each character vertex a unique index for internal representation.

STEP 4: Define a function edge(int a, int b) to add an edge between vertices a and b in the adjacency list.

STEP 5: Define BFS function bfs(int u) that:

Initializes queue q and pushes starting vertex u.

Marks u as visited: v[u] = true.

While the queue is not empty:

Pop a vertex n.

Print its character label.

For all adjacent vertices of n, if unvisited, push into queue and mark visited.

STEP 6: In main(), read number of vertices n and edges a.

STEP 7: Read n character labels and assign them indices using a map<char,int> and store in a vector.

STEP 8: Read a edges as character pairs and convert them to indices, then call edge(x, y).

STEP 9: Loop through all vertices and call bfs(i) for unvisited vertices to cover disconnected components.

STEP 10: End the program.




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

<img width="525" height="562" alt="519162840-6ca16f92-9ad8-4d55-95fe-d6f195582157" src="https://github.com/user-attachments/assets/272c7827-c034-4a63-81a3-f491a55024e5" />


 ## Result:
The program prints the BFS traversal of a graph with character-labeled vertices.

