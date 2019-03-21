---
title: 排序Java版
category: Algorithm
tag: Sort
---

### 冒泡排序
---


**基本思想：**
　　依次比较相邻的两个数，将小数放在前面，大数放在后面。即在第一趟：首先比较第n个和第n-1个，将小数放前，大数放后。然后比较第n-1个数和第n-2个数，将小数放前，大数放后，如此继续，直至全部排序完成。


``` java
 /**
    * 冒泡排序
    * @param 数组
    * @return 排好序的数组
    */
    static int[] BubbleSort(int[] a) {
    for (int i = a.length-1; i >= 0; i--) {
                for (int j = i; j > 0; j--) {
                    if(a[j]<a[j-1])
                        swap(a, j, j-1);
                }
        }
    return a;
    }
    static void swap(int[] a,int i,int j) {
        int t=a[i];
        a[i]=a[j];
        a[j]=t;
    }

```

### 插入排序
---


**基本思想：**
　　把n个待排序的元素看成一个有序表和一个无序表，开始时有序表中只有一个元素，无序表中有n-1个元素；排序过程即每次从无序表中取出第一个元素，将它插入到有序表中，使之成为新的有序表，重复n-1次完成整个排序过程。


``` java
/**
 *  插入排序Eg：
         [9| 7, 4, 0, 5]
        [7, 9| 4, 0, 5]
        [4, 7, 9| 0, 5]
        [0, 4, 7, 9| 5]
        [0, 4, 5, 7, 9]
    */
static int[] InsertSort (int a[]) {    
    int t=0;
    for (int i = 1; i < a.length; i++) {
        t=a[i];
            for (int j = i-1 ; j >= 0; j--) {
                    if(t<a[j])
                        swap(a,j,j+1);
                    else
                        continue;
            }
//  System.out.println(Arrays.toString(a));
    }     
    return a;
}
```