## char*

```c++
#include <iostream>
#include <cstring>
using namespace std;
int main(){
	size_t size=500;
	char* str1=new char[size];
	char* str2=new char[size];
	cout<<"enter first sentence \n";
	cin.get(str1,size);
	cin.ignore();
	cout<<"enter second sentence \n";
	cin.get(str2,size);
	cout<<"size of first sentence is "<<strlen(str1)<<"characters \n";
	cout<<strcat(str1,str2)<<endl;
	cout<<"size of first sentence is after concat is "<<strlen(str1)<<"characters \n";
	for(int i=0;i<strlen(str1);i++)
		cout<<(isdigit(str1[i]));
	cout<<endl;
	for(int i=0;i<strlen(str1);i++)
		cout<<(bool)(isalpha(str1[i]));
	delete [] str1;
	delete [] str2;
	return 0;
}
```

## string

