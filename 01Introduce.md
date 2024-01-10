# Algorithm

[bilibili](https://www.bilibili.com/video/BV1BU4y1b7RK/)
[class](https://cs170.org/)

Big O --- <=

little o --- <

Big $\Omega$ --- >=

little $\Omega$ --- >

$\Theta$ --- ==

## divide and conquer

$$
T(n) = \alpha T(n/b) + O(n^d)
$$

$\alpha$ subproblems of size $n/b$ , conbine time is $O(n^d)$

$$
T(n)=\left\{
\begin{matrix}
O(n^d) \qquad if\quad  d > \log_b\alpha \\
O(n^d\log{N}) \qquad if\quad  d = \log_b\alpha \\
O(n^{\log_b{N}}) \qquad if\quad  d < \log_b\alpha \\
\end{matrix}
\right.
$$

快速排序： 随机一个值作为元， 左边小于元，右边大于元 --- 递归

快速选择： 随即选择一个作为元， 如果目标比这个值小，则只在左边找，否则在右边。

这个的时间：$T(n) \leqslant T(n/2) + C(n)$ -- C: 比较的时间
最坏情况：每次一次都需要找最大的块

此时元的选择会对算法时间产生很大影响。 ---- 如何选择元？

select(A,k)
方法：

- 将数组A五个一组的集合
- B：每个数组的中值组成的数组
- P：元 P = select(B, n/10)
- L -- {<P} , R -- {>p}
- if k == |L|+1 return p
  elif k <= |L| return select (L,k)
  else return select(R, k-|L|-1)
