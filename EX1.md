# Ex.No:1

# Ex.Name:Write A C++ Program to represent the Adjacency Matrix

## Date:
## Aim:
To represent a graph using an adjacency matrix in C++, where a 2D array is used to indicate edges between vertices.

## Algorithm:
STEP 1: Start the program.

STEP 2: Define a 2D array vertArr[20][20] to store the adjacency matrix. Initialize all elements to 0.

STEP 3: Define a function add_edge(int u, int v) to add an edge between vertex u and vertex v:

Set vertArr[u][v] = 1

Set vertArr[v][u] = 1 (for undirected graph)

STEP 4: Define a function displayMatrix(int v) to print the adjacency matrix:

Loop through all vertices i and j

Print vertArr[i][j]

STEP 5: In main(), define the number of vertices (x = 6) and two variables for edges (a, b).

STEP 6: Read 6 edges from the user using a loop.

STEP 7: Call add_edge(a, b) for each input pair to fill the adjacency matrix.

STEP 8: Call displayMatrix(x) to display the adjacency matrix.

STEP 9: End the program.




## Program:
```
#include<iostream>
using namespace std;
int vertArr[20][20]; 
int count = 0;
void displayMatrix(int v) 
{
    int i,j;
    for(i=0;i<v;i++)
    {
        for(j=0;j<v;j++)
        {
            cout<<vertArr[i][j]<<" ";
        }
        cout<<endl;
    }
}
void add_edge(int u, int v) 
{      
    vertArr[u][v] = 1;
    vertArr[v][u] = 1;
  
}
int main() 
{
    int x=6,a,b;
   for(int i=0;i<6;i++)
   {
       cin>>a>>b;
        add_edge(a,b);
   }
   displayMatrix(x);
   return 0;
   return 0;
}
```


## Output:
<img width="577" height="775" alt="519161332-f9100426-37f5-4622-aff4-f3f192d4e777" src="https://github.com/user-attachments/assets/3e43a68f-1f3f-4b59-9789-07cf2c32d14b" />



 ## Result:
The program creates a graph with 6 edges based on user input and displays its adjacency matrix.

