Це сутність що присвоює назву для послідовності команд (тіло функції), яку потім можна викликати за заданою їй назвою.


Синтаксис:
```c++
 повертаємий_тип назва_функції(вхідні_параметри){
	 тіло_функції
 }
 ```

Приклад :
```c++
#include <iostream>

bool isOdd(int input){
	bool result = input%2;
	return result;
}

int main(){
	for(int i=0;i<10;i++){
		std::cout<<"number "<<i;
		if(isOdd(i))
			std::cout<<" is odd"<<std::endl; 
		else
			std::cout<<" isn\'t odd"<<std::endl;
	}
}
}```
