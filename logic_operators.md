
### if - оператор гілкування

if(*"умова"*)
{
	*"тіло оператора"*
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

---
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

---
### логічні оператори

&& - і (повертає "так"  тільки, якщо обидві умови рівні "так")
```c++
#include <iostream>
int main(){
	std::cout<<(true&&true)<<"\n";
	std::cout<<(false&&true)<<"\n";
	std::cout<<(true&&false)<<"\n";
	std::cout<<(false&&false)<<"\n";
}
```
>1
>0
>0
>0

|| - або (повертає "ні"  тільки, якщо обидві умови рівні "ні")
```c++
#include <iostream>
int main(){
	std::cout<<(true||true)<<"\n";
	std::cout<<(false||true)<<"\n";
	std::cout<<(true||false)<<"\n";
	std::cout<<(false||false)<<"\n";
}
```
>1
>1
>1
>0

! - не (перетворює "так" в "ні" а "ні" в "так")
```c++
#include<iostream>
int main(){
	bool boolvar=true;
	std::cout<<boolvar<<" "<<!boolvar<<"\n";
	boolvar=false;
	std::cout<<boolvar<<" "<<!boolvar<<"\n";
}
```
>1 0

>0 1