# algorithms-demos

## 冒泡排序（Bubble sort）

**介绍**：比较相邻的两个数，如果后面的比前面的小，把小的放在前面。

**时间复杂度**:  O(n^2)

**动画演示**：[冒泡排序](http://www.webhek.com/post/comparison-sort.html)

**实际代码**：
```javascript
/**
对比arr中的第j+1项和第j项，如果第j+1项小于第j项，就把第j+1项和第j项调换位置。如果没达到最终的顺序（从小到大），就继续找，继续换，直到达到最终效果
*/ 
function bubbleSort(arr) {
    for(var i = 0; i < arr.length - 1; i++) {
        for(var j = 0; j < arr.length - 1; j++) {
            if (arr[j+1] < arr[j]) {
                temp = arr[j+1];
                arr[j+1] = arr[j];
                arr[j] = tmp;
            }
        }
    }
    return arr;
}
```
但是上面的方法并不完美，如果数组已经是有序了，就没必要再比较了，所以下面有一种优化冒泡排序算法：
```javascript
function bubbleSort(arr){
    var flag = false;  // 定义一个变量为false，未交换位置
    for(var i=0;i<arr.length-1;i++){
        for(var j=0;j<arr.length-1;j++){
            if(arr[j+1]<arr[j]){
                temp = arr[j+1];
                arr[j+1] = arr[j];
                arr[j] = temp;
                flag = true; //true，已交换位置
            }
        }
        if(flag){
            flag = false; //如果交换了位置，将flag重新设为false
        }else{
             break;       //如果未交换，则跳出循环
        }
    }
    return arr;
}
// 或者
function bubbleSort(arr){
    var flag;
    for(var i=0;i<arr.length-1;i++){
        flag =false;
        for(var j=0;j<arr.length-1;j++){
            if(arr[j+1]<arr[j]){
                temp = arr[j+1];
                arr[j+1] = arr[j];
                arr[j] = temp;
                flag = true;
            }
        }
        if(!flag){
            return arr;
        } 
    }
    return arr;
}
```

## 选择排序（selection Sort）

**介绍**：在乱序的数组中选择最小的值，然后和每次循环后的数组的第一位进行交换

**时间复杂度**:  O(n^2)

**动画演示**：[选择排序](http://www.webhek.com/post/comparison-sort.html)

**实际代码**

```javascript
```