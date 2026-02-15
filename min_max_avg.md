Пошук мінімального, максимального та середнього значень — це базові операції при роботі з масивами та контейнерами даних.

---

### Коли використовувати

| Операція | Метод                                 | Опис                                                |
| -------- | ------------------------------------- | --------------------------------------------------- |
| `Min`    | Ручний перебір або `std::min_element` | Знаходження найменшого елемента в наборі даних.     |
| `Max`    | Ручний перебір або `std::max_element` | Знаходження найбільшого елемента в наборі даних.    |
| `Avg`    | Сумування або `std::accumulate`       | Обчислення середнього арифметичного всіх елементів. |

---

### Приклади

#### 1. Пошук мінімуму (Min)
```c++
#include <iostream>
#include <algorithm>
#include <ctime>

int main() {
    const size_t size = 10;
    int array[size];
    srand(time(0));

    for(int i = 0; i < size; i++) {
        array[i] = rand() % 100;
        std::cout << array[i] << " ";
    }
    std::cout << std::endl;

    // Ручний пошук
    int min = array[0];
    for(int i = 1; i < size; i++)
        if(min > array[i]) min = array[i];

    // Використання STL
    int* min_ptr = std::min_element(std::begin(array), std::end(array));

    std::cout << "Min (manual): " << min << "\n";
    std::cout << "Min (STL): " << *min_ptr << std::endl;
    return 0;
}
```

#### 2. Пошук максимуму (Max)
```c++
#include <iostream>
#include <algorithm>

int main() {
    int array[] = {10, 50, 20, 80, 30};
    size_t size = sizeof(array)/sizeof(array[0]);

    // Ручний пошук
    int max = array[0];
    for(int i = 1; i < size; i++)
        if(max < array[i]) max = array[i];

    // Використання STL
    auto max_ptr = std::max_element(std::begin(array), std::end(array));

    std::cout << "Max: " << *max_ptr << std::endl;
    return 0;
}
```

#### 3. Середнє значення (Avg)
```c++
#include <iostream>
#include <numeric>

int main() {
    int array[] = {1, 2, 3, 4, 5};
    size_t size = 5;

    // Ручне сумування
    int sum = 0;
    for(int i = 0; i < size; i++) sum += array[i];
    float avg_manual = (float)sum / size;

    // Використання std::accumulate
    double sum_stl = std::accumulate(std::begin(array), std::end(array), 0.0);
    double avg_stl = sum_stl / size;

    std::cout << "Avg: " << avg_stl << std::endl;
    return 0;
}
```

---

### Теги
#min #max #average #algorithms #stl

