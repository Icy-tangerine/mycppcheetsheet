## shell sort

Задає відстнь між порівнюваними елементами в половину розміру масиву і перевіряє всі парина цій відстані, тоді ділить відстань на 2 і знову проходить по всьому масиву, і продовжує ділити відстань на 2 поки вона не дойде до 1 тобто порівнюватись будуть сусідні елементи, в кінці цього проходу масив буде відсортовано.
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
	for(int d = size/2;d>=1;d/=2)
		for(int i=d;i<size;i++)
			for(int j=i;j>=d&&array[j-d]>array[j];j-=d){
				int tmp=array[j];
				array[j]=array[j-d];
				array[j-d]=tmp;
			}
  //printing array
  for(int i=0;i<size;i++){
    cout<<array[i]<<" ";
  }
  cout<<endl;
}
```
