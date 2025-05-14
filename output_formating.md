## setw
задає ширину строки що виводиться
```c++
#include <iostream>
#include <iomanip>
int main(){
	std::cout<<std::setw(30)<<"text"<<std::setw(10)<<1234<<std::endl;
}
```
## left right
вирівнюють вивід по лівій чи правій стороні

```c++
#include <iostream>
#include <iomanip>
int main(){
	std::cout<<std::setw(30)<<std::left<<"text"
		<<std::setw(10)<<std::right<<1234<<std::endl;
}
```

## setfill
задає зимвол для заповнення пропусків
``` c++
#include <iostream>
#include <iomanip>
int main(){
	std::cout<<std::setw(30)<<std::setfill('-')<<"text"<<std::endl;
}
```

## setprecision
задає точність при виведенні числа з плаваючою крапкою
```c++
#include <iostream>
#include <iomanip>
int main(){
	std::cout<<std::setprecision(2)<<3.14159<<" "<<12234.56789;
}
```
## fixed
закріпляє крапку при виведенні числа з плаваючою крапкою, не дає виводитись в науковому представленні
```c++
#include <iostream>
#include <iomanip>
int main(){
	std::cout<<std::fixed<<std::setprecision(2)<<3.14159<<" "<<12234.56789;
}
```