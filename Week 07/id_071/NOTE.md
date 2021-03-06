# NOTE

  > 位运算


    0100  4(d)
    01000 8(d)
    0101  5(d)

    位运算符
        << 左移  0011 => 0110
        >> 右移  0110 => 0011
        | 按位或   0011 | 1011 => 1011
        & 按位与   0011 & 1011 => 1100
        ~ 按位取反 0011 => 1100
        按位异或 ^ 0011 ^ 1011 => 1000 
        
        异或操作 相同为0不同为1  不进位加法
        
        x^0 = x
        x ^1s = ~x //1s = ~0
        x ^(~x) = 1s
        x ^ x = 0
        c = a ^ b => a ^ c = b,b ^ c = a
        a ^ b ^ c = a^(b^c) = (a^b)^c

    算数移位
        x 最右边的n位清零  x & (~0 << n)
        获取x的第n位值(0 1) (x >> n)&1

    位运算应用
        判断奇偶
            x%2 == 1 --> (x & 1) == 1
            x%2 == 0 --> (x & 1) == 0
        x >> 1 -> x/2
            mid = (left+right)/2;--> mid = (left+right)>>1
        x = x & (x-1) 清零最低位的 1
        x & -x => 得到最低位的1
        x & ~x => 0


****

> 布隆过滤器 LRU缓存

##### bloom filter 布隆过滤器

    一个很长的二进制向量和一系列随机映射函数。布隆过滤器可以用于检索一个元素是否在一个集合中


    优点是 空间效率 和 查询时间 都 远远超过一般的算法
    缺点是 有一定的误识别率 和 删除困难
    

##### LRU缓存  least recently used

    LFU least frequently used

    两个要素 大小、替换策略
    Hash Table + Double Linkedlist
    查询 O(1)
    修改 更新 O(1)

****

> 排序算法

##### 初级排序O(n^2)

    选择排序  每次找最小值 然后放到待排序数组的起始位置

    插入排序 从前到后逐步构建有序序列，对于未排序数据，在已排序学历中从后向前扫描，找到相应位置并插入

    冒泡排序  相邻元素如果逆序 则交换
    
##### 高级排序O(nlogn)

    快速排序 quick sort 
        数组取标杆 pivot 将小元素放pivot 左边，大元素放右侧，然后一次对右边和右边的子数组继续快排，以达到整个序列有序
        
    归并排序 merge sort - 分治 
        先排序左右子数组，然后合并两个有序子数组
        
    堆排序 heap sort 堆插入 O(logn) 取最大最小 O(1)

##### 特殊排序

