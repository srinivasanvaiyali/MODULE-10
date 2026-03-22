# Ex.No:5

# Ex.Name: Write A C++ Program for Topological Sorting (using vector and algorithm STLs)

## Date:
## Aim:
To perform Topological Sorting of a directed acyclic graph (DAG) using vectors and STL algorithms in C++.

## Algorithm:
STEP 1: Start the program.

STEP 2: Represent the DAG as a list of edges or pairs, where pair(a,b) means an edge from a → b.

STEP 3: Define a pair structure to store edges and a comparator to sort them in topological order.

STEP 4: Use vector to store all edges.

STEP 5: Sort the vector using std::sort and the custom comparator.

STEP 6: In the comparator, ensure that a < b or b < a is used to determine the topological order.

STEP 7: Iterate through the sorted vector and print each edge or vertex in order.

STEP 8: End the program.




## Program:
```
#include <iostream>
#include <vector>
#include <algorithm>

struct pair 
{
	int a, b;
	pair(int a, int b) : a(a), b(b) {}
	
	std::ostream &print(std::ostream &out) const 
	{
		return (out << "(" << a << ", " << b << ")");
	}
};

std::ostream &operator<<(std::ostream &out, const pair &p) 
{ 
    return p.print(out); 
    
}

struct topological_pair_comparator 
{
	bool operator()(const pair &p, const pair &q) const 
	{ 
	    return p.a<q.a && p.b<q.b; 
	    
	}
} tpc;

std::vector<pair> pairs = 
{
     pair(1,1),
    pair(1,2),
	pair(2,1),
	pair(3,1),
	pair(1,3),
	pair(5,5),
	pair(2,2),
	pair(4,0)

//write code here
};

int main() {
	std::sort(pairs.begin(), pairs.end(), tpc);
	for(const pair &p : pairs) std::cout << p << " ";
	std::cout << std::endl;
	return 0;
}
```



## Output:
<img width="1169" height="280" alt="519164405-576ebc75-d556-47db-a269-397888d3e275" src="https://github.com/user-attachments/assets/9d780341-22cb-43c6-8289-a56c10e9f56c" />



 ## Result:
 The program sorts the vertices (or edges) of a DAG in topological order.

