<script src="https://leetcode-cn.com/problems/intersection-of-two-linked-lists/"></script>

<script src="//onlinegdb.com/embed/js/OjbRZTr2g?theme=light"></script>


{% klipse "eval-js", loopMsec="1000" %}
new Date()
{% endklipse %}


{% klipse "eval-python", gistId="jackymxp/681cd4b4fe195300905b48fb2776050e" %}
{% endklipse %}


```eval-cpp
#include <iostream>
 
using namespace std;
 
template<typename T>
class BubbleSort {
public:
    void bubbleSortIterative(T *arr, const int len) {
        bubbleSortIterative(arr, 0, len - 1);
        // assert(isSorted(arr, len) == true);
    }
 
    void bubbleSortRecursive(T *arr, const int len) {
        bubbleSortRecursive(arr, 0, len - 1);
        // assert(isSorted(arr, len) == true);
    }
 
    void bubbleSortAdvanced(T *arr, const int len) {
        bubbleSortAdvanced(arr, 0, len - 1);
        // assert(isSorted(arr, len) == true);
    }
 
private:
    void bubbleSortIterative(T *arr, const int lo, const int hi) {
        for (int i = hi; i >= lo + 1; i--) {
            bubbleOperator(arr, i);
            // assert(isSorted(arr, i, hi));
        }
    }
 
    void bubbleSortRecursive(T *arr, const int lo, const int hi) {
        if (lo >= hi)
            return;
        bubbleOperator(arr, hi);
        bubbleSortRecursive(arr, lo, hi - 1);
    }
 
    void bubbleSortAdvanced(T *arr, const int lo, const int hi) {
        for (int i = hi; i >= lo + 1; i--) {
            if (bubbleOperatorAdvanced(arr, i))
                return;
            // assert(isSorted(arr, i, hi));
        }
    }
 
    //在arr[0...hi]做冒泡过程，将最大值放在arr[hi]位置
    inline void bubbleOperator(T *arr, const int hi) {
        for (int i = 0; i < hi; i++)
            if (arr[i] > arr[i + 1])
                swap(arr, i, i + 1);
    }
 
    //没有发生交换返回true
    inline bool bubbleOperatorAdvanced(T *arr, const int hi) {
        bool isSort = true;
        for (int i = 0; i < hi; i++) {
            if (arr[i] > arr[i + 1]) {
                swap(arr, i, i + 1);
                isSort = false;
            }
        }
        return isSort;
    }
 
    void swap(T *arr, const int i, const int j) {
        T k = arr[i];
        arr[i] = arr[j];
        arr[j] = k;
    }
 
    bool isSorted(T *arr, const int lo, const int hi) {
        for (int i = lo; i < hi; i++)
            if (arr[i] > arr[i + 1])
                return false;
        return true;
    }
 
    bool isSorted(T *arr, const int len) {
        return isSorted(arr, 0, len - 1);
    }
};
 
int main(void){
    srand(time(NULL));
    BubbleSort<int> bubbleSort;
    const int len = 10000;
    int* arr = new int[len];


    for(int i = 0; i < len; i++)
        arr.push_back(rand()%len);
    bubbleSort.bubbleSortIterative(&arr[0], len);
    return 0;
}
 

```

<script src="https://snippets.cacher.io/snippet/d635afe4965230ee9159"></script>

<script src="https://gist.github.com/ouqiang/2f22a86e32d1bb53832f.js"></script>
