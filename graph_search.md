

[[bfs&dfs.gif]]
## Breadth first search
 Обхід в ширину
```c++
#include <iostream>
#include <queue>
using namespace std;

int main(){
	queue<int> Queue;
	const int n = 7;

	int mas[n][n]={
		{0,1,1,0,0,1,0},
		{1,0,0,0,0,0,0},
		{1,0,0,1,0,0,0},
		{0,0,1,0,1,0,0},
		{0,0,0,1,0,0,0},
		{1,0,0,0,0,0,1},
		{0,0,0,0,0,1,0} };

	int tops[n];
	for(int i=0;i<n;i++)
		tops[i]=0;

	Queue.push(0);
	
	while(!Queue.empty()){
		int top= Queue.front();
		Queue.pop();
		tops[top]=2;

		for(int j=0;j<n;j++){
			if(mas[top][j]==1&&tops[j]==0){
				Queue.push(j);
				tops[j]=1;
			}
		}
		for(int i=0;i<n;i++){
			cout<<tops[i]<<" ";
		}
		cout<<endl;
		cout<<top+1<<endl;
	}
	return 0;
}

```


## Depth first search
Обхід в глибину
```c++
#include <iostream>
#include <stack>
using namespace std;

int main(){
	stack<int> Stack;
	const int n = 7;

	int mas[n][n]={
		{0,1,1,0,0,1,0},
		{1,0,0,0,0,0,0},
		{1,0,0,1,0,0,0},
		{0,0,1,0,1,0,0},
		{0,0,0,1,0,0,0},
		{1,0,0,0,0,0,1},
		{0,0,0,0,0,1,0} };

	int tops[n];
	for(int i=0;i<n;i++)
		tops[i]=0;

	Stack.push(0);
	
	while(!Stack.empty()){
		int top= Stack.top();
		Stack.pop();

		if(tops[top]==2)continue;
		tops[top]=2;

		for(int j=n-1;j>=0;j--){
			if(mas[top][j]==1&&tops[j]!=2){
				Stack.push(j);
				tops[j]=1;
			}
		}
		for(int i=0;i<n;i++){
			cout<<tops[i]<<" ";
		}
		cout<<endl;
		cout<<top+1<<endl;
	}
	return 0;
}
```
