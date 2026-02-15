Базові алгоритми сортування зазвичай мають складність $O(n^2)$ і є простими у реалізації. Вони підходять для невеликих масивів або навчальних цілей.

## Порівняння алгоритмів

| Алгоритм | Складність | Опис |
|----------|------------|------|
| **Bubble Sort** | $O(n^2)$ | Послідовно порівнює сусідні елементи та міняє їх місцями. |
| **Selection Sort** | $O(n^2)$ | Шукає мінімальний елемент у залишку масиву і ставить його на початок. |
| **Insertion Sort** | $O(n^2)$ | Вставляє кожен наступний елемент у правильну позицію серед уже відсортованих. |

---

## Bubble Sort (Бульбашкове сортування)
Проходить по всьому [масиву](static_array.md) міняючи місцями сусідні елементи поки масив не буде посортовано:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;
int main(){
  const size_t size=30;
  int array[size];
  //filling array
  for(int i =0;i<size;i++){
    array[i]=rand()%100;
    cout<<array[i]<<" ";
  }
  cout<<endl;
  //sorting array
  for(int i=0;i<size-1;i++){
    for(int j=0;j<size-i-1;j++){
      if(array[j]>array[j+1]){
        int temp=array[j];
        array[j]=array[j+1];
        array[j+1]=temp;
      }
    }
  }
  //printing array
  for(int i=0;i<size;i++){
    cout<<array[i]<<" ";
  }
  cout<<endl;
}
```

---

## Selection Sort (Сортування вибором)
Проходить по всьому масиву справа від теперішнього елемента, шукає найменший елемент і ставить його на місце теперішнь��го елемента:

```cpp
#include <iostream>
using namespace std;
int main(){
  const size_t size=30;
  int array[size];
  //filling array
  for(int i =0;i<size;i++){
    array[i]=rand()%100;
    cout<<array[i]<<" ";
  }
  cout<<endl;
//sorting array
  for(int i=0;i<size-1;i++){
    int min=i;
    for(int j=i+1;j<size;j++){
      if (array[j]<array[min]) {
        min=j;
      }
    }
    if(min!=i){
      int tmp=array[i];
      array[i]=array[min];
      array[min]=tmp;
    }
    
  }
//printing array
  for(int i=0;i<size;i++){
    cout<<array[i]<<" ";
  }
  cout<<endl;
}
```

---

## Insertion Sort (Сортування вставками)
Проходить по всьому масиву і переміщає кожен елемент вліво поки не знайде менший за нього елемент:

```cpp
#include <iostream>
using namespace std;
int main(){
  const size_t size=30;
  int array[size];
  //filling array
  for(int i =0;i<size;i++){
    array[i]=rand()%100;
    cout<<array[i]<<" ";
  }
  cout<<endl;
  //sorting array
  for(int i=0;i<size;i++){
    for(int j=i;j>0&&array[j]<array[j-1];j--){
      int tmp=array[j];
      array[j]=array[j-1];
      array[j-1]=tmp;
    }
  } 
  //printing array
  for(int i=0;i<size;i++){
    cout<<array[i]<<" ";
  }
  cout<<endl;
}
```

---

## std::sort
Можна використати алгоритм з стандартної бібліотеки [\<algorithm>](source_file_inclusion.md):

```cpp
#include <iostream>
#include <algorithm>
using namespace std;
int main(){
  const size_t size=30;
  int array[size];
  for(int i =0;i<size;i++){
    array[i]=rand()%100;
    cout<<array[i]<<" ";
  }
  cout<<endl;
  
  sort(begin(array),end(array));
  //sort(begin(array),end(array),less<int>()); //to sort by ascending
  //sort(begin(array),end(array),greater<int>()); //to sort by descending
  for(int i=0;i<size;i++){
    cout<<array[i]<<" ";
  }
  cout<<endl;
}
```

---

## Теги
#sorting #algorithms #bubblesort #selectionsort #insertionsort #stdsort
