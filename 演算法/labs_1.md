GenAI_Algorithm_lab1 ==> 二元搜尋樹的各種實作(heap sort)
提問詞:請寫出二元搜尋樹的演算法
提問詞:請計算二元搜尋樹演算法的時間複雜度
提問詞:請用Python寫出二元搜尋樹的演算法
提問詞:請用C寫出二元搜尋樹的演算法
提問詞:請用C++寫出二元搜尋樹的演算法
提問詞:請用JAVA寫出二元搜尋樹的演算法
提問詞:請用Rust寫出二元搜尋樹的演算法
提問詞:請用go寫出二元搜尋樹的演算法
提問詞:請用C#寫出二元搜尋樹的演算法
提問詞:請用Javascript#寫出二元搜尋樹的演算法

# GenAI_Algorithm_lab1 ==> heap sort的各種實作
- `提問詞`:請寫出heap sort的演算法
- `提問詞`:請計算heap sort演算法的時間複雜度
- `提問詞`:請用Python寫出heap sort的演算法
- `提問詞`:請用C寫出heap sort的演算法
- `提問詞`:請用C++寫出heap sort的演算法
- `提問詞`:請用JAVA寫出heap sort的演算法
- `提問詞`:請用Rust寫出heap sort的演算法
- `提問詞`:請用go寫出heap sort的演算法
- `提問詞`:請用C#寫出heap sort的演算法
- `提問詞`:請用Javascript#寫出heap sort的演算法



'''
建堆 (Build Heap)：將未排序的陣列轉換成一個最大堆。
排序 (Sort)：重複以下步驟直到陣列已排序：
將堆的根節點（即最大值）與最後一個節點交換，然後減少堆的大小。
將新的根節點進行堆化，使其保持最大堆性質。
Pseudocode
pseudo
Copy code
function heapSort(arr):
    n = length(arr)

    // Step 1: Build a max heap
    for i = floor(n / 2) - 1 to 0:
        heapify(arr, n, i)

    // Step 2: Extract elements from the heap one by one
    for i = n - 1 to 0:
        // Move current root to end
        swap(arr[0], arr[i])
        
        // Call max heapify on the reduced heap
        heapify(arr, i, 0)

function heapify(arr, n, i):
    largest = i      // Initialize largest as root
    left = 2 * i + 1 // left child
    right = 2 * i + 2 // right child

    // If left child is larger than root
    if left < n and arr[left] > arr[largest]:
        largest = left

    // If right child is larger than largest so far
    if right < n and arr[right] > arr[largest]:
        largest = right

    // If largest is not root
    if largest != i:
        swap(arr[i], arr[largest])

        // Recursively heapify the affected sub-tree
        heapify(arr, n, largest)
Python 代碼實現
python
Copy code
def heapify(arr, n, i):
    largest = i
    left = 2 * i + 1
    right = 2 * i + 2

    if left < n and arr[left] > arr[largest]:
        largest = left

    if right < n and arr[right] > arr[largest]:
        largest = right

    if largest != i:
        arr[i], arr[largest] = arr[largest], arr[i]
        heapify(arr, n, largest)

def heapSort(arr):
    n = len(arr)

    for i in range(n // 2 - 1, -1, -1):
        heapify(arr, n, i)

    for i in range(n - 1, 0, -1):
        arr[i], arr[0] = arr[0], arr[i]
        heapify(arr, i, 0)

# 測試範例
arr = [12, 11, 13, 5, 6, 7]
heapSort(arr)
print("排序後的陣列是:", arr)
解釋
建堆 (Build Heap)：
從最後一個非葉子節點開始，向上逐個節點進行堆化操作。
這保證了所有的非葉子節點都滿足最大堆性質。
排序 (Sort)：
將堆頂元素（最大值）與堆的最後一個元素交換，並將堆的大小減1。
對新的根節點進行堆化，重新維持最大堆性質。
重複這個過程，直到堆的大小縮小為1，排序完成。
時間複雜度
建堆的時間複雜度是 
𝑂
(
𝑛
)
O(n)。
每次提取最大元素並重新堆化的時間複雜度是 
𝑂
(
log
⁡
𝑛
)
O(logn)，共進行 
𝑛
−
1
n−1 次。
總時間複雜度是 
𝑂
(
𝑛
log
⁡
𝑛
)
O(nlogn)。
這個算法的主要優點是穩定的時間複雜度 
𝑂
(
𝑛
log
⁡
𝑛
)
O(nlogn) 並且不需要額外的內存空間。

- Online C Compiler
  - [Online C Compiler - Programiz](https://www.programiz.com/c-programming/online-compiler/)
'''
