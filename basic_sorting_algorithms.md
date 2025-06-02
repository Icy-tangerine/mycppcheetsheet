## bubble sort 

Проходить по всьому [масиву](static_array.md) міняючи місцями сусідні елементи поки масив не буде посортовано:
```c++
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

## selection sort 
Проходить по всьому масиву справа від теперішнього елемента, шукає найменший елемент і ставить його на місце теперішнього елемента:
```c++
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
## insertion sort 
Проходить по всьому масиву і переміщає кожен елемент вліво поки не знайде менший за нього елемент:
```c++
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

```c++
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