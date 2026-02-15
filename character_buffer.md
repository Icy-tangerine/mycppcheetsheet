Робота з текстовими даними в C++ може здійснюватися двома основними способами: через C-style рядки (`char*`) або через клас `std::string`.

## Порівняння способів

| Характеристика | `char*` (C-style) | `std::string` (C++) |
|----------------|-------------------|---------------------|
| **Тип** | Вказівник на масив символів | Клас-контейнер |
| **Пам'ять** | Керується вручну (`new`/`delete`) | Керується автоматично |
| **Безпека** | Низька (ризик переповнення буфера) | Висока |
| **Функції** | Бібліотека `<cstring>` (`strlen`, `strcpy`) | Методи класу (`size`, `find`, `substr`) |

---

## C-style рядки (`char*`)
Це масиви символів, що закінчуються нульовим символом (`\0`). Вимагають обережного поводження з пам'яттю.

```cpp
#include <iostream>
#include <cstring>
using namespace std;
int main(int argc,char** argv){
	size_t size=500;
	char* str1=new char[size];
	cout<<"enter first sentence \n";
	cin.getline(str1,size);
	cout<<"size of first sentence is "<<strlen(str1)<<" characters \n";
	cout<<"numbers in str1\n";
	for(int i=0;i<strlen(str1);i++)
		cout<<isdigit(str1[i]);
	cout<<"\nletters in str1\n";
	for(int i=0;i<strlen(str1);i++)
		cout<<(bool)isalpha(str1[i]);
	cout<<"\nuppercase letters in str1\n";
	for(int i=0;i<strlen(str1);i++)
		cout<<(bool)isupper(str1[i]);
	cout<<"\nlowercase letters in str1\n";
	for(int i=0;i<strlen(str1);i++)
		cout<<(bool)islower(str1[i]);
	delete [] str1;
	return 0;
	}
```

---

## Клас `std::string`
Сучасний спосіб роботи з рядками в C++. Він автоматично розширюється і надає зручні методи для пошуку та маніпуляції текстом.

```cpp
#include <iostream>
#include <string>

int main(){
	std::string str;
	std::cout<<"enter a sentence \n";
	std::cin>>str;
	if(str.find('e')>str.size())
		std::cout<<"letter \"e\" isn't present in a sentence";
	else
		std::cout<<"letter \"e\" is located at "<<str.find('e')+1;
	std::cout<<"\nsubstring from 1 to 3 element of a string "<<str.substr(1,3);
}
```

---

## Теги
#strings #char #buffer #stdstring