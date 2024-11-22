## min
Щоб знайти найменше значення можна скористатись таким методом:
```c++
#include <iostream>
using namespace std;
int main(){
  const size_t size=30;
  int array[size];
  srand(time(0));
  for(int i =0;i<size;i++){
    array[i]=rand()%100;
    cout<<array[i]<<" ";
  }
  cout<<endl;
//finding minimal value
  int min=array[0];
  for(int i=0;i<size;i++)
    if(min>array[i])
      min=array[i];
 //printing minimal value
  cout<<"min= "<<min;
}
```

Або можна скористатись функцією std::min_element() з бібліотеки  [\<algorithm>](source_file_inclusion)
```c++
#include <iostream>
#include <algorithm>
using namespace std;
int main(){
  const size_t size=30;
  int array[size];
  srand(time(0));
  for(int i =0;i<size;i++){
    array[i]=1+rand()%100;
    cout<<array[i]<<" ";
  }
  cout<<endl;
//finding minimal value
  int* min=min_element(begin(array),end(array));
  
 //printing minimal value
  cout<<"min= "<<*min;
}
```

---
## max
Найбільше значення в масиві можна знайти так само як і найменше але з переверненим знаком:
```c++
#include <iostream>
using namespace std;
int main(){
  const size_t size=30;
  int array[size];
  srand(time(0));
  for(int i =0;i<size;i++){
    array[i]=rand()%100;
    cout<<array[i]<<" ";
  }
  cout<<endl;
//finding minimal value
  int max=array[0];
  for(int i=0;i<size;i++)
    if(max<array[i])
      max=array[i];
 //printing minimal value
  cout<<"max= "<<max;
}
```

Або функцією std::max_element() з бібліотеки  [\<algorithm>](source_file_inclusion)
```c++
#include <iostream>
#include <algorithm>
using namespace std;
int main(){
  const size_t size=30;
  int array[size];
  srand(time(0));
  for(int i =0;i<size;i++){
    array[i]=1+rand()%100;
    cout<<array[i]<<" ";
  }
  cout<<endl;
//finding maximum value
  int* max=max_element(begin(array),end(array));
  
 //printing maximum value
  cout<<"max= "<<*max;
}
```

---
## avg
Середнє значення можна знайти таким алгоритмом:
```c++
#include <iostream>
using namespace std;
int main(){
  const size_t size=30;
  int array[size];
  srand(time(0));
  for(int i =0;i<size;i++){
    array[i]=1+rand()%100;
    cout<<array[i]<<" ";
  }
  cout<<endl;
  int sum=0;
  for(int i=0;i<size;i++){
    sum+=array[i];
  }
  float avg=(float)sum/size;
  
  //printing average
  cout<<"avg= "<<avg;
}
```
Або з використанням функції std::accumulate() з бібліотеки [\<numeric>](source_file_inclusion)
```C++
#include <iostream>
#include <numeric>
using namespace std;
int main(){
  const size_t size=30;
  int array[size];
  srand(time(0));
  for(int i =0;i<size;i++){
    array[i]=1+rand()%100;
    cout<<array[i]<<" ";
  }
  cout<<endl;
  float avg=accumulate(begin(array),end(array),0.0)/size;
  
 //printing average value
  cout<<"avg= "<<avg;
}
```