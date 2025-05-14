## shell sort

Задає відстнь між порівнюваними елементами в половину розміру масиву і перевіряє всі парина цій відстані, тоді ділить відстань на 2 і знову проходить по всьому масиву, і продовжує ділити відстань на 2 поки вона не дойде до 1 тобто порівнюватись будуть сусідні елементи, в кінці цього проходу масив буде відсортовано.
```c++
#include <iostream>
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
	for(int d = size/2;d>=1;d/=2)
		for(int i=d;i<size;i++)
			for(int j=i;j>=d&&array[j-d]>array[j];j-=d){
				swap(array[j],array[j-d]);
			}
  //printing array
  for(int i=0;i<size;i++){
    cout<<array[i]<<" ";
  }
  cout<<endl;
}
```


## merge sort
рекурсивно ділить масив пополам поки не дойде до частин розміром в 1 елемент тоді від об'єднує елементи в зростаючому чи спадаючому порядку

```c++
#include <iostream>
#include <iomanip>
using namespace std;
void merge(int* arr,int left,int mid,int right){
		//setting distance from start to mid 
		int n1 = mid - left + 1;
		//and from mid to end
    int n2 = right - mid;


		int* Lhalf=new int[n1];
		int* Rhalf=new int[n2];
		//filling temporary array with data from first half of array
		for(int i=0;i<n1;i++)
			Lhalf[i]=arr[left+i];
		//filling temporary array with data from second half of array
		for(int i=0;i<n2;i++)
			Rhalf[i]=arr[mid+1+i];
		
		int i=0,j=0,k=left;
		//writing data from temporary arrays to original array in sorted order
		while(i<n1 && j<n2){
			if(Lhalf[i]<=Rhalf[j]){
				arr[k]=Lhalf[i];
				i++;
			}else{
				arr[k]=Rhalf[j];
				j++;
			}
			k++;
		}
		//writing remaining data into original array
		while(i<n1){
			arr[k]=Lhalf[i];
			i++;k++;
		}
		while(j<n2){
			arr[k]=Rhalf[j];
			j++;k++;
		}	
		//reseasing the allocated for temporary arrays memory
		delete[] Lhalf;
		delete[] Rhalf;
}
void mergesort(int* arr,int left,int right){
	int mid;
	//when length of array is greater then 1
	if(left<right){
		//setting the mid point to split the array
		mid=left+(right-left)/2;
		//calling this function while passing into it the first half of array
		mergesort(arr,left,mid);
		//calling this function while passing into it the second half of array
		mergesort(arr,mid+1,right);
		//when splitting is done we get out of this funciton to start merging
		merge(arr,left,mid,right);
		//when two halves are merged we get out of this function
	}
}
void print(int* arr,size_t size){
	for(int i=0;i<size;i++)
		cout<<setw(4)<<arr[i];
}
int main(){
	size_t size=20;
	int* arr=new int[size];
//filling array
	for(int i=0;i<size;i++){
		arr[i]=10+rand()%50;
	}
//printing unsorted array
	print(arr,size);
	cout<<endl;
//sorting the array
	mergesort(arr,0,size-1);

//printing sorted array
	print(arr,size);
	cout<<endl;
	return 0;
}
```