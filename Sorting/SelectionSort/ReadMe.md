## Introduction

Similar to bubble sort, but instead of first placing largest values at the end, we will place smallest values at the start.

## Alogrithm
- Store the index of first element in a variable minIndex.
- Take one pointer i which will start from the beginning of the array and loop through the whole length. 
- Take another pointer j which will start from the next element of the current location of the first pointer.Loop thorugh the end of the array. If any element is smaller than the first element, keep replacing the value of minIndex with that index. This way, we find the index of the minimum number.
- If value of i doesnt match with minIndex, swap their elemnts.
- Keep on looping
- return the sorted array

<img src="https://upload.wikimedia.org/wikipedia/commons/9/94/Selection-Sort-Animation.gif"
     alt="Markdown Monster icon"
     style="float: left; margin-right: 10px;" />
 
<img src="https://www.w3resource.com/w3r_images/selection-short.png"
     alt="Markdown Monster icon"
     style="float: left; margin-right: 10px;" />

```java

   static int[] selectionSort(int[] arr){
    int minIndex = 0;
    for(int i=0;i<arr.length;i++){
      minIndex = i;
      for(int j=i+1;j<arr.length;j++){
        if(arr[j]<arr[minIndex]){
          minIndex = j;
        }
      }
      if(minIndex!=i){
        int temp = arr[i];
        arr[i] = arr[minIndex];
        arr[minIndex] = temp;
    return arr;
  }
```


## Time Complexity
- Worst Case: O(n^2)
- Best Case: O(n^2), no change. As we are traversing the whole array either way

## Space Complexity
- Constant for both cases

## Special Note
Both bubble and selection sort is bad, but in some cases, selection sort is better to use than using bubble sort. For example if you want to reduce the number of **swap** operation, selection sort is better.
