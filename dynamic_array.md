Вказівники також можуть вказувати на динамічно виділену пам'ять для одного чи декількох елементів певного типу.

Динамічно виділяти пам'ять можна з допомогою виразу new:

```c++
#include <iostream>
int main(){
	size_t size=0;
	std::cout<<"enter size of array"<<std::endl;
	std::cin>>size;

	//allocating memory
	int* array= new int[size];

	//writing into memory
	for(int i=0;i<size;i++)
		array[i]=rand();

	//reading from memory
	for(int i=0;i<size;i++)
		std::cout<<array[i]<<std::endl;

	//releasing memory
	delete [] array;
	return 0;
}
```

тут ми вводимо з клавіатури бажаний розмір масиву, тоді виразом new ми виділяємо потрібну кількість пам'яті і адресу першого байта виділеної пам'яті ми записуємо у [[pointer|вказівник]] під назвою array. Потім ми звертаємось до виділеної пам'яті і записуємо в неї випадкові значення що генерує   [[functions|функція]]   [[random|rand()]]  