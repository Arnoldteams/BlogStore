---
title: 查找Java版
category: Algorithm
tag: Search
---

### 顺序查找
---


**基本思想：**
　　依次比较相邻的两个数，将小数放在前面，大数放在后面。即在第一趟：首先比较第n个和第n-1个，将小数放前，大数放后。然后比较第n-1个数和第n-2个数，将小数放前，大数放后，如此继续，直至全部排序完成。


``` java
 /**
 * 顺序查找
 * @param 数组；查找的元素
 * @return 下标
 */
static int SequenceSearch(int[] a,int num) {
    for (int i = 0; i < a.length; i++) {
            if(a[i]==num)
                    return i+1;
        }
    return -1;
}

```

### 折半（二分）查找
---


**基本思想：**
　　搜索过程从数组的中间元素开始，如果中间元素正好是要查找的元素，则搜索过程结束；如果某一特定元素大于或者小于中间元素，则在数组大于或小于中间元素的那一半中查找，而且跟开始一样从中间元素开始比较。如果在某一步骤数组为空，则代表找不到。这种搜索算法每一次比较都使搜索范围缩小一半。仅限有序数组


``` java
 /**
 * 二分查找(只能查找有序数组)
 * @param 数组；查找的元素
 * @return 下标
 */
    static int BinarySearch(int[] a,int num) {
        int low = 0;
        int high = a.length-1;
        int mid;
        while(low<=high) {
            mid = (low + high) / 2;
            if(a[mid] > num) {
                    high=mid-1;
            }else if(a[mid] < num) {
                    low=mid+1;
            }else {
                    return mid+1;
            }
        }    
        return -1;
    }

```