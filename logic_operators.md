Логічні оператори та оператори розгалуження дозволяють керувати потоком виконання програми залежно від певних умов.

---

### Основні оператори

| Оператор          | Назва              | Опис                                               |
| ----------------- | ------------------ | -------------------------------------------------- |
| `if` / `else`     | Умовний оператор   | Виконує блок коду, якщо умова істинна.             |
| `? :`             | Тернарний оператор | Скорочена форма `if-else` для повернення значення. |
| `&&`              | Логічне "І" (AND)  | Істинно, якщо обидва операнди істинні.             |
| <code>\|\|</code> | Логічне "АБО" (OR) | Істинно, якщо хоча б один операнд істинний.        |
| `!`               | Логічне "НЕ" (NOT) | Змінює значення на протилежне.                     |



---

### Приклади

#### 1. Оператор розгалуження (if - else)
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

#### 2. Тернарний оператор
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

#### 3. Логічні оператори (&&, ||, !)
```c++
#include <iostream>
int main(){
	// Логічне "І" (&&)
	std::cout << (true && true) << "\n";   // 1
	std::cout << (false && true) << "\n";  // 0

	// Логічне "АБО" (||)
	std::cout << (true || false) << "\n";  // 1
	std::cout << (false || false) << "\n"; // 0

	// Логічне "НЕ" (!)
	bool boolvar = true;
	std::cout << boolvar << " " << !boolvar << "\n"; // 1 0
}
```

---

### Теги
#logic #operators #if-else #ternary 