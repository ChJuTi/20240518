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
**建立最大堆積（Max Heap）**或最小堆積（Min Heap）：
如果要遞增排序，則建立最大堆積，使父節點的值大於子節點。
如果要遞減排序，則建立最小堆積，使父節點的值小於子節點。
排序過程：
將最大（或最小）元素（即堆積的根節點）與未排序部分的最後一個元素交換。
縮小堆積範圍，排除已排序的元素。
重複上述步驟，直到整個陣列排序完成。
以下是使用 JavaScript 實作的堆積排序程式碼：

JavaScript

Array.prototype.heap_sort = function() {
    const arr = this.slice(0);

    function swap(i, j) {
        const tmp = arr[i];
        arr[i] = arr[j];
        arr[j] = tmp;
    }

    function max_heapify(start, end) {
        let dad = start;
        let son = dad * 2 + 1;

        if (son >= end) return;

        if (son + 1 < end && arr[son] < arr[son + 1]) son++;

        if (arr[dad] < arr[son]) {
            swap(dad, son);
            max_heapify(son, end);
        }
    }

    const len = arr.length;

    for (let i = Math.floor(len / 2) - 1; i >= 0; i--) {
        max_heapify(i, len);
    }

    for (let i = len - 1; i > 0; i--) {
        swap(0, i);
        max_heapify(0, i);
    }

    return arr;
};

const inputArray = [3, 5, 3, 0, 8, 6, 1, 5, 8, 6, 2, 4, 9, 4, 7, 0, 1, 8, 9, 7, 3, 1, 2, 5, 9, 7, 4, 0, 2, 6];
const sortedArray = inputArray.heap_sort();
console.log(sortedArray);
AI 產生的代碼。請仔細檢視及使用。 深入了解常見問題集。
這段程式碼會將 inputArray 進行堆積排序，並輸出排序後的結果。如果有其他問題，歡迎詢問！12

- Online C Compiler
  - [Online C Compiler - Programiz](https://www.programiz.com/c-programming/online-compiler/)
'''
