# 8.2 插入排序

## 直接插入排序 Insert Sort

代码实现

```cpp
void InsertSort(int A[], int n) {
int i, j;
for (i = 2; i <= n; i++)
    if (A[i] < A[i - 1]) {
        A[0] = A[i];
        for (j = i - 1; A[0] < A[j]; j--)
            A[j + 1] = A[j];
        A[j + 1] = A[0];
    }
}
```

## 折半插入排序

代码实现 TODO

## 希尔排序 Shell Sort （缩小增量排序）

- 代码 TODO

<!-- ### 习题

- 1 对于5个不同的数据元素进行直接插入排序，最多需要进行的比较次数是（不包含与哨兵的比较）→10次；解析：4+3+2+1=10次，如果加上与哨兵的比较就是14次（5+4+3+2）
- 3【2012】 对同一待排序序列分别进行折半插入排序和直接插入排序，两者之间可能的不同之处是
A. 排序的总趟数
B. 元素的移动次数
C. 使用辅助空间的数量
D. 元素之间的比较次数→D.元素之间的比较次数；
解析：
用 折半插入排序 的比较次数的数量级在$O(n\log_2n)$ ，
用 直接插入排序 的比较次数和初始状态有关，在$O(n)\sim O(n^2)$ 之间
- 4 对有 n 个元素的顺序表采用直接插入排序算法进行排序，在最坏情况下所需的比较次数是多少？最好情况呢？（不考虑和哨兵的比较）?→最坏情况 ( n - 1 ) n / 2，最好情况 n - 1
- 12【2009】 用希尔排序方法对一个数据序列排序，若第1趟排序结果为` 9 1 4 13 7 8 20 23 15` ，则采用的增量间隔可能是 ?→3
- 18【2015】希尔排序的组内排序采用的是
A 直接插入排序
B 折半插入排序
C 快速排序
D 归并排序→A 直接插入排序
- 19【2018】 -->
