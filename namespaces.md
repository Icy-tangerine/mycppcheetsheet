Простори імен використовуються для запобігання конфліктів імен (коли декілька змінних чи функцій мають однакове ім'я)

namespace "*назва простору імен*"
{
	"*оголошення*"
}


```c++
#include <iostream>
int number =5;
int number =10;//error: refedinition of 'number'
int main(){
std::cout<<number<<std::endl;
}
```

>помилка через перевизначення змінної

```c++
#include <iostream>
namespace first_ns_name{
	int number=5;
}
namespace second_ns_name{
	int number=10;
}
int main(){
	std::cout<<first_ns_name::number<<std::endl;
	std::cout<<second_ns_name::number<<std::endl;
}
```

>5

>10

