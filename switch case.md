передає контроль блокам коду відповідно до умови

switch("*умова*")
{
	case "*варіант умови*":
		"*тіло що виконується якщо умова рівна варіанту мови*"
}

```c++
#include <iostream>
int main(){
	int i=0;
	std::cout<<"input a number\n";
	std::cin>>i;
	switch(i){
		case 1:
			std::cout<<"first case triggered\n";
		case 2:
			std::cout<<"second case triggered\n";
		default:
			std::cout<<"default case triggered\n";
	}
}
```

>input a number
>2
>second case triggered
>default case triggered

щоб вийти з тіла switch після виконання певного коду можна використати ключове слово break

```c++
#include <iostream>
int main(){
	int i=0;
	std::cout<<"input a number\n";
	std::cin>>i;
	switch(i){
		case 1:
			std::cout<<"first case triggered\n";
			break;
		case 2:
			std::cout<<"second case triggered\n";
			break;
		default:
			std::cout<<"default case triggered\n";
	}
}
```

>input a number
>2
>second case triggered

https://en.cppreference.com/w/cpp/language/switch