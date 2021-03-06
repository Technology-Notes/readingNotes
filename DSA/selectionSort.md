# 选择排序

> 选择排序是排序算法中很基础也是大家学习算法的过程中最先遇到的几个算法之一，同时它的思想也非常的简单。

## 游戏时间

上体育课了，现在老师说大家按个头，从高到矮依次排列，有哪些方法可以选择呢？其中一种简单的方法就是，第一个同学先站出来，记好自己站的位置，然后就开始从第二个同学开始，跟每个人比身高，如果遇到了比自己高的，那第一位同学就站回去，又这位长得高的同学站出来，然后继续往下比。那么当遍历一遍所有的同学过后，外面站着的就是这些同学中最高的，然后这个同学就和最后的那位同学换个位置。

好了，现在最高的同学已经排好序了，下面我们以此进行剩下的比较，最后排序完毕。

## 如何实现

```js
function selectionSort(arr) {
  // 我们每一次都选择最高的同学，总共有 n 个同学，我们就要遍历 n 次
  const n = arr.length;
  for(let i = n - 1; i >= 0; i--) {
    // 我们先把身高最高的同学的位置记下来
    let index = i;
    // 用 n - i 是因为，最后一位都是最高的了，就没必要去比较了
    for(let j = 0; j < n - i; j++) {
      // 当然啦，同学肯定不和自己比，没意思
      if (i !== j) {
        // 当后面的同学身高更高的时候，就把这位同学的位置记下来
        if (arr[j] > arr[index]) {
          index = j;
        }
      }
    }
    // 交换记录下来的身高最高的这位同学和最后一位同学
    swap(arr, index, n - 1 - i);
  }
  return arr;
}
```

## 大 O 是多少？

我们可以看到要遍历 n 个同学，同时每个同学都还要去跟其他同学比较，也就是 n * 1/2 * n，在大 O 的表示中，常数是忽略的，也就是O(n*n)