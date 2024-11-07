
### if - оператор розгалуження

if(*умова*)
{
	*тіло оператора*
}
else
{
	*тіло оператора*
}
```c++
#include <iostream>
using namespace std;
int main()
{
	int number;
	cout<<"input a number"<<endl;
	cin >> number;
	if(number<0){
		cout<<"negative"<<endl;
	}else if(number>0){
		cout<<"positive"<<endl;
	}else{
		cout<<"equal to zero"<<endl;
	}
}
```

### Тернарний оператор гілкування
*умова* ? *тіло при виконанні умови* : *тіло при НЕ виконанні умови*

```c++
#include <iostream>
using namespace std;
int main()
{
	int number;
	cout<<"input a number"<<endl;
	cin>>number;
	cout<<(number>0?"positive":"negative")<<endl;
}
```
