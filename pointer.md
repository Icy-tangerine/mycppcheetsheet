це змінна що може зберігати в собі адресу іншої змінної

```c++
#include <iostream>
int main(){
	int variable = 10;
	int* pointer = &variable;
	std::cout<<"variable address = "<<&variable<<"  | variable value = "<<variable<<std::endl;
	std::cout<<"pointer value =    "<<pointer<<"  | value by this address = "<<*pointer<<std::endl;
	*pointer+=5;
	std::cout<<"new variable value = "<<variable<<std::endl;
	return 0;
}
```

> variable address = 0x7ffda9bcb084  | variable value = 10
> 
>pointer value =        0x7ffda9bcb084  | value by this address = 10
>
>new variable value = 15

Таким чином можна змінювати дані змінної коли немає прямого доступу до неї.

```c++
#include <iostream>
int main(){
	int variable = 10;//creating variable
	int* pointer = &variable;//creating pointer and initializing it with variable address
	int copy = *pointer;//creating copy of variable
	variable+=5;//adding 5 to a variable
	std::cout<<"variable = "<<variable<<//variable changed to 15
		"\npointer = "<<*pointer<<//pointer shows updated value of variable
		"\ncopy = "<<copy<<std::endl;//copy hasn't been changed
	return 0;
}
```

>variable = 15
>pointer = 15
>copy = 10

Ще вказівники та посилання це єдиний спосіб доступитись до динамічно виділеної пам'яті