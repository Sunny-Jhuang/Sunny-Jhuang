![image](https://user-images.githubusercontent.com/90752081/138622874-735ef9ba-29ad-4733-887e-90a0cdc65ecb.png)
# 上图是基于IP协议传输的一个数据包
```
第一部分是IP协议头。
第二部分是TCP协议头，这部分的基础大小为20字节，如果带上可选项(options)，可能更大。
第三部分是TCP数据包，一般是从更上层协议带来的数据。
```
![image](https://user-images.githubusercontent.com/90752081/138593255-e2e3e999-5fc5-4507-b756-ac84ac474b38.png)
# TCP Header
```
除了options外有5行，每行32bits，即4字节。
Source Port和Destination Port，源端口和目标端口，由于ip地址是由ip协议管理的，所以这里没有ip。
Sequence Number，序列号，在一次TCP连接中，由连接的一方发出的数据包，序列号是递增的，递增量取决于数据部分大小。
Acknowledgment Number，确认号，用于对序列号进行确认。
Header Length，表示整个TCP头(包括options)的大小。
Resv，保留位，留给新的标志位使用。
8个标志位，每一位有0和1两种值，一般称值为1的位为置位。
Window Size，窗口大小，用于告诉对方，自己这里还有多少空间可以用来处理对方发来的数据。
TCP CheckSum，TCP协议的安全保障手段，对TCP头部和数据两部分加密校验。
Urgent Pointer，紧急指针，在URG置位时有效，它是一个正向的偏移量，表示Sequence Number至Sequence Number+Urgent Pointer部分的数据是紧急数据，和PSH标志位相似，这也是一个约定，收到紧急指针的一方可以按自己的方式处理。
Options，这部分长度可变，最多是40字节。
```
