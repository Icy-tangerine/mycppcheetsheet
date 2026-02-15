Для введення та виведення даних у C++ використовуються стандартні потоки. Основна бібліотека для роботи з ними — `<iostream>`. Вона надає об'єкти `cin` для читання та `cout` для запису даних.

---

### Основні інструменти

| Об'єкт      | Назва            | Опис                                                 |
| ----------- | ---------------- | ---------------------------------------------------- |
| `std::cout` | Character Output | Використовується для виведення даних у консоль.      |
| `std::cin`  | Character Input  | Використовується для зчитування даних з клавіатури.  |
| `std::endl` | End Line         | Переходить на новий рядок та очищує буфер виводу.    |
| `\n`        | New Line         | Просто переходить на новий рядок (швидше за `endl`). |

---

### Приклади

#### 1. Виведення даних (cout)
```c++
#include <iostream>
using namespace std;

int main() {
    int y = 5;
    cout << "y = " << y << endl;
    return 0;
}
```
**Результат:**
> y = 5

#### 2. Введення даних (cin)
```c++
#include <iostream>
using namespace std;

int main() {
    int y = 0;
    cout << "Enter a number: " << endl;
    cin >> y;
    cout << "You entered: " << y << endl;
    return 0;
}
```
**Результат:**
> Enter a number:
> 8
> You entered: 8

---

### Теги
#iostream #cin #cout #input #output 

