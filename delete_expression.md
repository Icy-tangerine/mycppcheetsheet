Викликає деструктор об'єкта, на який вказує вказівник, що ми їй подаємо, а потім вивільняє виділену, за допомогою new, пам'ять, на яку вказує даний їй вказівник.

є дві реалізації delete:
> 'delete pointer'   для вивільнення пам'яті вказівників, що не являються масивами

> 'delete[] pointer' для вивільнення пам'яті вказівників, що являються масивами

```c++
#include <iostream>
int main(){
	//allocating memory
	int* num= new int;
	int* array= new int[5];
	//generating data
	*num=5;
	for(int i=0;i<5;i++)
		array[i]=5-i;
	//writing data
	std::cout<<"num = "<<*num<<";\n";
	std::cout<<"array:\n";
	for(int i=0;i<5;i++)
		std::cout<<array[i]<<"\n";
	std::cout<<std::endl;
	//releasing memory
	delete num;
	delete[] array;

	return 0;
}
```
