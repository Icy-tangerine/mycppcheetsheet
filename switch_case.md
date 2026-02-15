Оператор `switch` передає керування одному з декількох блоків коду (case) залежно від значення цілочисельного виразу.

---

### Коли використовувати

| Ситуація | Чому підходить |
|----------|----------------|
| Багато варіантів однієї змінної | Читабельніша альтернатива довгим ланцюжкам `if-else if`. |
| Меню вибору | Ідеально для обробки вибору користувача (наприклад, 1, 2, 3 або 'a', 'b', 'c'). |
| Перерахування (enum) | Ефективно працює з типами `enum`. |

---

### Приклади

#### 1. Базовий switch (без break)
Якщо не використовувати `break`, виконання "провалюється" у наступні кейси.
```c++
#include <iostream>

int main() {
    int i;
    std::cout << "Input a number: ";
    std::cin >> i;
    switch(i) {
        case 1:
            std::cout << "First case triggered\n";
        case 2:
            std::cout << "Second case triggered\n";
        default:
            std::cout << "Default case triggered\n";
    }
    return 0;
}
```

#### 2. Switch з використанням break
`break` зупиняє виконання всередині `switch` і виходить з нього.
```c++
#include <iostream>

int main() {
    int i;
    std::cout << "Input a number: ";
    std::cin >> i;
    switch(i) {
        case 1:
            std::cout << "First case triggered\n";
            break;
        case 2:
            std::cout << "Second case triggered\n";
            break;
        default:
            std::cout << "Default case triggered\n";
            break;
    }
    return 0;
}
```

---

### Теги
#switch #control-flow #basics
