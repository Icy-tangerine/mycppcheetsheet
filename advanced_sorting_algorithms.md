Алгоритми сортування з покращеною складністю (зазвичай $O(n \log n)$ або адаптивні) використовуються для обробки великих масивів даних, де базові алгоритми ($O(n^2)$) працюють занадто повільно.

## Порівняння алгоритмів

| Алгоритм       | Складність (середня) | Складність (найгірша) | Особливості                                                               |
| -------------- | -------------------- | --------------------- | ------------------------------------------------------------------------- |
| **Shell Sort** | $O(n \log^2 n)$      | $O(n^2)$              | Покращене сортування вставками, не потребує додаткової пам'яті.           |
| **Merge Sort** | $O(n \log n)$        | $O(n \log n)$         | Стабільне сортування, потребує $O(n)$ додаткової пам'яті.                 |
| **Heap Sort**  | $O(n \log n)$        | $O(n \log n)$         | Використовує структуру даних "купа", не потребує додаткової пам'яті.      |
| **Quick Sort** | $O(n \log n)$        | $O(n^2)$              | Найшвидший на практиці, але нестабільний і має поганий найгірший випадок. |

---

## Shell Sort (Сортування Шелла)
Це вдосконалений варіант сортування вставками. Замість порівняння сусідніх елементів, він порівнює елементи на певній відстані (`gap`), яка поступово зменшується.

```cpp
void shellSort(int arr[], int n) {
    for (int gap = n / 2; gap > 0; gap /= 2) {
        for (int i = gap; i < n; i++) {
            int temp = arr[i];
            int j;
            for (j = i; j >= gap && arr[j - gap] > temp; j -= gap) {
                arr[j] = arr[j - gap];
            }
            arr[j] = temp;
        }
    }
}
```

---

## Merge Sort (Сортування злиттям)
Рекурсивний алгоритм, що працює за принципом "розділяй і володарюй". Він ділить масив навпіл, сортує кожну частину і зливає їх у впорядкований масив.

```cpp
void merge(int arr[], int l, int m, int r) {
    int n1 = m - l + 1;
    int n2 = r - m;
    int* L = new int[n1];
    int* R = new int[n2];

    for (int i = 0; i < n1; i++) L[i] = arr[l + i];
    for (int j = 0; j < n2; j++) R[j] = arr[m + 1 + j];

    int i = 0, j = 0, k = l;
    while (i < n1 && j < n2) {
        if (L[i] <= R[j]) arr[k++] = L[i++];
        else arr[k++] = R[j++];
    }
    while (i < n1) arr[k++] = L[i++];
    while (j < n2) arr[k++] = R[j++];

    delete[] L;
    delete[] R;
}

void mergeSort(int arr[], int l, int r) {
    if (l < r) {
        int m = l + (r - l) / 2;
        mergeSort(arr, l, m);
        mergeSort(arr, m + 1, r);
        merge(arr, l, m, r);
    }
}
```

---

## Heap Sort (Пірамідальне сортування)
Використовує бінарну купу (binary heap). Спочатку будується "max-heap", де корінь — найбільший елемент, потім корінь міняється з останнім елементом і купа перебудовується.

```cpp
void heapify(int arr[], int n, int i) {
    int largest = i;
    int l = 2 * i + 1;
    int r = 2 * i + 2;

    if (l < n && arr[l] > arr[largest]) largest = l;
    if (r < n && arr[r] > arr[largest]) largest = r;

    if (largest != i) {
        std::swap(arr[i], arr[largest]);
        heapify(arr, n, largest);
    }
}

void heapSort(int arr[], int n) {
    for (int i = n / 2 - 1; i >= 0; i--)
        heapify(arr, n, i);

    for (int i = n - 1; i > 0; i--) {
        std::swap(arr[0], arr[i]);
        heapify(arr, i, 0);
    }
}
```

---

## Quick Sort (Швидке сортування)
Вибирає опорний елемент (`pivot`) і переставляє елементи так, щоб зліва були менші за нього, а справа — більші. Потім рекурсивно повторює це для обох частин.

```cpp
int partition(int arr[], int low, int high) {
    int pivot = arr[high];
    int i = (low - 1);
    for (int j = low; j < high; j++) {
        if (arr[j] < pivot) {
            std::swap(arr[++i], arr[j]);
        }
    }
    std::swap(arr[i + 1], arr[high]);
    return (i + 1);
}

void quickSort(int arr[], int low, int high) {
    if (low < high) {
        int pi = partition(arr, low, high);
        quickSort(arr, low, pi - 1);
        quickSort(arr, pi + 1, high);
    }
}
```

---

## Теги
#sorting #algorithms #shellsort #mergesort #heapsort #quicksort 