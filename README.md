#### 知识点归纳
- 同步和异步：

  在离散时间更新状态 => 同步时序系统
  在任意时间更新状态 =>异步时序系统
  $$
  eg：对D触发器来讲，异步加在SR端，同步加在D端
  $$
  
- 数制转换的小数部分：数值的小数部分重复乘以新的基数，保存结果的整数部分，直到小数部分为0。新的数制下的数字按计算结果的整数顺序排列。如果新的基数 > 10, 把所有大于10的余数用数字A, B, … 表示

  $$
  eg：0.6875转换为2进制，\\
  0.6875\times2=1.375，\\0.375\times2=0.75,\\0.75\times2=1.5,\\0.5\times2=1;\\
  0.6875=2^{-1}+2^{-3}+2^{-4}=0.1011
  $$
  注意添0

- 标准形式：

  积之和（SOP）：找1项

  和之和（POS）：找0项

- 成本标准：

  文字成本 (L)：数字母数
  $$
  eg：F = BD + AB'C + A C'D'\\                     L = 8
  $$
  门输入成本(G)：L+与或门数（两个以上字母在一起的个数）
  $$
  eg：F = BD + AB’C + AC’D’\\                  G = 11
  $$
  

  含非门的门输入成本(GN)：L+G+非门数（一种字母计算一次）
  $$
  eg：F =  BD+AB’C+AB’D’+ABC’ \\GN=18
  $$

- 缓冲器：是一个电子信号放大器，以便于输出端可以连接更多的门，或者用来减少信号通过电路的时间

  F=X:

![在这里插入图片描述](https://img-blog.csdnimg.cn/835c04c5c01d4fe68c4a6c754bd0674c.png)


- 与非门（与完再非），等价于非完再或

  或非门（或完再非），等价于非完再与

- 异或运算的拓展（用于全加器）

  奇函数：与二变量函数**只需要一个变量的值为1**相比，三变量或者三变量以上的函数则**需要奇数个变量的值为1**。所以，**多变量异或运算**又被定义为奇函数（odd function）。事实上，严格说来，这才是三变量或者三变量以上运算的正确含义，“异或”这个名字只适合于二变量。

  奇函数的反/倒相即偶函数

  奇函数和偶函数在卡诺图上呈现“跳棋棋盘” 样式（如图）
  奇函数的卡诺图中标有1的格子对应于最小项,它的索引号(二进制)含奇数个1，偶函数则含偶数个1.
  $$
  eg：下图为1项为：001，010，100，111，均含奇数个1
  $$
 ![image](https://img-blog.csdnimg.cn/img_convert/0e79ecf7011d3ce252c78abfabad772f.png)



- 校验/产生偶校验字:用奇函数
  校验/产生奇校验字:用偶函数
  eg：
  n = 3. 产生一个4位偶校验字的校验位,使用奇函数:
  操作: (X,Y,Z) = (0,0,1) ,P=1
  (X,Y,Z,P) = (0,0,1,1) , E = 0.
  如果传输时Y从0变成1,那么E = 1表示错误.
![在这里插入图片描述](https://img-blog.csdnimg.cn/9182e130af8a48a9845b97188ae9abd9.png)


- 三态门与高阻态输出：

  三个输出状态：0，1，Hi-Z

  加了Hi-Z后逻辑门的特性：

  - 有三个输出值
  - **能把两个输出端连在一起（期中考点）**
  - 信号能从两个方向向另一个方向进行单向传输

- 三态缓冲器：

  数据输入IN加控制输入（使能）EN

  EN：OUT=Hi-Z

  ~EN：OUT=IN

![在这里插入图片描述](https://img-blog.csdnimg.cn/5866486248fa4290b2e6b4edcba9d01f.png)


  eg：把两个三态缓冲器的输出B1和B0连在一起, 成为一个输出端OUT
  假设:缓冲器的输入可以是任意0和 1的组合
  规则:至少一个缓冲器的输出值必须为Hi-Z,为什么?

  因为输入可以是任意的组合，包括（0，1）和（1，0），若没有Hi-Z输出，则可能会产生高电流，破坏电路。

  对两个三态门的连接,有多少个有效的输入输出组合存在?

  5

  对n个三态缓冲器输出端连接成一个输出,有什么规则?

  n-1个输出必须为Hi-Z

  有多少个有效的输入输出组合存在?

  2n+1：每个缓冲器可输出0、1，则其他全为Hi-Z，2n种组合，加上全为Hi-Z，即2n+1.

  三态逻辑用于数据选择：

  优点：由于  EN0 = ~S 以及EN1 = S, 其中一个三态缓冲器的输出总是Hi-Z，OL总是分别由IN0和IN1确定

![在这里插入图片描述](https://img-blog.csdnimg.cn/7b48fecff4bb47b886da8a674f421ab6.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_13,color_FFFFFF,t_70,g_se,x_16)


- 基本逻辑函数：

  定值：F=0，F=1

  传递：F=X

  取反：F=~X

- 译码器的扩展：对原始的两个译码器的输出端分别用与门相连

  eg：两个1-2译码器构成2-4译码器

![在这里插入图片描述](https://img-blog.csdnimg.cn/620e95aabb364c14adf3f8f3eb4f634f.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_15,color_FFFFFF,t_70,g_se,x_16)


- 译码器加或门实现通用逻辑（原理：最小项之和）

  eg：

  P1、P2、P4分别为A7、A6、A5、A3的函数，先将4位A进行4-16译码，有16个输出，对应16个最小项，再对3位P求最小项之和，用或门实现求和

  P1 = Sum(1,2,5,6,8,11,12,15)

  P2 = Sum(1,3,4,6,8,10,13,15)

  P4 = Sum(2,3,4,5,8,9,14,15)

![在这里插入图片描述](https://img-blog.csdnimg.cn/c0ce903a280a488d8ff97588234c7baa.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_18,color_FFFFFF,t_70,g_se,x_16)


- 优先编码器：

  因为译码器的输出只有一个为1，对其简单的反操作不能适应所有的输入组合，比如出现两个1。

  一个适合于任意输入组合，并能产生有意义的结果的编码器称为优先编码器。在所有出现的1中，选择输入值位置包含1的最高位（或者最低位)，来产生这个位置对应的二进制编码。

  eg：

  只考虑1项，如A1的1项为8、4，分别为D4'D3和D4'D3'D2，再求和
![在这里插入图片描述](https://img-blog.csdnimg.cn/d70739f65f0541efac5423cb44eac00d.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_20,color_FFFFFF,t_70,g_se,x_16)
![在这里插入图片描述](https://img-blog.csdnimg.cn/3df52fe6b9664c3c92d69ef111ddc711.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_20,color_FFFFFF,t_70,g_se,x_16)


- 多路复用器：

  - 译码器+使能+或门

  eg：4-1多路复用器，选择端S1S0经2-4译码后，产生4项。只有1项为1，与门和输入连接，故只有一个输入有效，再或门输出这一个有效值。
![在这里插入图片描述](https://img-blog.csdnimg.cn/cce3d00b6d4542bd90244c0d684bff0a.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_20,color_FFFFFF,t_70,g_se,x_16)


  - 三态门：每个选择端选择一半，持续二分选出最后一个

    eg：
![在这里插入图片描述](https://img-blog.csdnimg.cn/d1eb692ffae5482280382daa906a0482.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_19,color_FFFFFF,t_70,g_se,x_16)


- 多路复用器实现通用组合电路：

  - 直接接定值（0、1）信号

    对A->B的问题，先按A从大到小进行排序，再分别对B的每一位进行定值选择

    eg：
    ![在这里插入图片描述](https://img-blog.csdnimg.cn/470e4bd86aa54c68aacbcaa8c8b74d74.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_9,color_FFFFFF,t_70,g_se,x_16)
    ![在这里插入图片描述](https://img-blog.csdnimg.cn/1fe9b50947c84904ae61b8cfca8a2389.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_11,color_FFFFFF,t_70,g_se,x_16)



    以y为例，重新排序后，从000-111，y的对应输出为0、1、1、0、0、1、1、0。以000为例，内部即以IN1输入输出，故IN1接定值0即可，以此类推：
    ![在这里插入图片描述](https://img-blog.csdnimg.cn/d95b50d75f2d4101abfe9dce047f5899.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_10,color_FFFFFF,t_70,g_se,x_16)

    

  - A排序后，接A的最低位及其反相和定值，A的其余位用于选择

    eg：
    ![在这里插入图片描述](https://img-blog.csdnimg.cn/b2a462ee892a46b3887de494dd359981.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_20,color_FFFFFF,t_70,g_se,x_16)


    以y为例，每两种情况当成一种情况，分别可接C，~C,1,0。
    ![在这里插入图片描述](https://img-blog.csdnimg.cn/bddd5fcb1b744b8da06b0c5b4ac3027e.png)


- 迭代组合电路
![在这里插入图片描述](https://img-blog.csdnimg.cn/9dae83e9fe5d4f6e971a3edae60d18d8.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_20,color_FFFFFF,t_70,g_se,x_16)

  eg：n = 32
  输入个数 = 66(2n+2)
  真值表的行数 = 2^66

- 加法器：

  - 半加器：有进位，但无来自低位的进位
  $$
    和：S=X\bigoplus Y
$$
$$
    进位：C=XY
$$
  - 全加器：多了一位来自低位的进位输入。同样计算出一位和S及一位进位C
$$
    和：S=X\bigoplus Y \bigoplus Z（Z为低位的进位）
$$
$$
    进位：C=XY+(X\bigoplus Y)Z（需要传至高位）
$$
$$
    XY为进位产生G,
    X\bigoplus Y为**进位传播**P
$$
  - 超前进位加法器：相当于数列递推式求通式

    Si = Ai xor Bi xor Ci = Pi xor Ci

    Ci+1 = Ai Bi + Ai Ci + Bi Ci

    ​    = Ai Bi + Ci (Ai + Bi)

    ​    = Ai Bi + Ci (Ai xor Bi)

    ​    = Gi + Ci Pi

    C1 = G0 + P0 C0

    C2 = G1 + P1 C1 = G1 + P1 G0 + P1 P0 C0

    C3 = G2 + P2 C2 = G2 + P2 G1 + P2 P1 G0 + P2 P1 P0 C0

    C4 = G3 + P3 C3 = G3 + P3 G2 + P3 P2 G1 + P3 P2 P1 G0 + P3 P2 P1 P0 C0

  - 行波进位加法器：由多个全加器连接而成

    eg：4-位行波进位加法器
    ![在这里插入图片描述](https://img-blog.csdnimg.cn/2a2d8d3b570846bca142e97b3b8bdc10.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_20,color_FFFFFF,t_70,g_se,x_16)


- 减法：

  - 无符号减法：借位减法。当减不够时（即小减大），首位补1，再用相当于加上的数字减去结果。

    eg：
    ![在这里插入图片描述](https://img-blog.csdnimg.cn/764ea732218843fcad041451e42216a9.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_13,color_FFFFFF,t_70,g_se,x_16)


  - 反码（基数减1补码）与补码（反码+1）：

    补码的另一种求法：一个 n-位二进制数, 从最低位向高位走:拷贝所有最低的全0，拷贝第一个出现的1，对所有随后的为取反

    减法通过加上减数的补码完成
    如果结果为负, 对结果做补码运算

    eg：
    $$
    0100-0111\\
    0111+1001(0111的补码)\\
    =1101(因为结果为负，再取补码，为0011）
    $$

  - 有符号减法：

    - 数的表示：最高位为符号位，0正1负，正数=0+原数，负数=绝对值带符号位0的补码

    - 原码相加:同号求和，异号求差，

      原码相减:同号求差，异号求和，

      求和符号与前者同，求差符号与前者异

    - 补码算术

- 溢出检测：
$$
  overflow V = Cn \bigoplus Cn-1
$$
- 压缩：对输入端的值进行固定、传递和取反后，加到功能模块上，针对特定应用将已有电路简化成一个简单电路

  eg：递增（+1）
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/14ca93f83e9f477fac38f1999d721816.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_20,color_FFFFFF,t_70,g_se,x_16)


- 乘法的实现：直接赋值与加法器的使用

  eg：4位B乘以101
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/44a330b352ba4fe3a1bfb08db68117e3.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_20,color_FFFFFF,t_70,g_se,x_16)


- 组合电路的时序行为：

  - 波形图
  - 门延时：输入变化导致输出变化的时间

- S’-R’锁存器（交叉对与非门）：00为禁止输入组合

  S-R锁存器（交叉对或非门）：11为禁止输入组合

  时钟型S’-R’锁存器：在输入前再加两个与非门，当C=1时才进行操作

  D锁存器：时钟型锁存器的输入S为D，R为D’
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/d403147f69514842b83e5870c6af5d7a.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_16,color_FFFFFF,t_70,g_se,x_16)


- 锁存器的时序问题：会出现当C=1时，输出不断变化

  期望：每个时钟脉冲输出只变化一次

  方法：打断锁存器内输入到输出的路径

  主从型：时钟输入反相串联，等于说每个脉冲结束才把输入传到输出

  - 问题：延时；1捕获（假设主锁存器的输出为0，当主锁存器的S由0变1再变0，R保持为0时，主锁存器的输出变为1，这个1被捕获，会传到从锁存器中）

- D触发器
![在这里插入图片描述](https://img-blog.csdnimg.cn/dc34437f91b448ef9320f4955bd35130.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_14,color_FFFFFF,t_70,g_se,x_16)


  异步输入：加在SR端
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/5272cafa456a4ea9bd93e1b567a4f0eb.png)


  圈表示0有效

  0加到S，因为是与非门，Q复位为1

  0加到R，Q’变为1，Q置位为0

- 激励表：由当前状态和下一状态求输入

- 时序电路分析

  eg：
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/eda8743be868491e9b5cea90e2a92880.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_13,color_FFFFFF,t_70,g_se,x_16)


  A(t+1) = A(t)x(t) + B(t)x(t)=DA
  B(t+1) = ~A(t)x(t)=DB
  y(t) = ~x(t)(B(t) + A(t))

- 状态表：包含四个部分（当前状态+输入+下一状态+输出），时序电路的真值表

  eg：上题
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/a441af3cbb844fb8b88d6781aed65f91.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_20,color_FFFFFF,t_70,g_se,x_16)


- 状态图：

  - 含状态名的圆圈表示每个状态
  - 从当前状态到下一状态的有向弧线表示每个状态的转换
  - 有向弧线上写输入\输出

  eg:
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/94eb0f6106554e06a0e7807a35f0cd0f.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_19,color_FFFFFF,t_70,g_se,x_16)


- 等价状态：对应每个可能的输入序列，相同输出和下一状态都相同的两个状态

  eg:
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/a42fd6abeab446e69560d6aa1b8ceeb9.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_15,color_FFFFFF,t_70,g_se,x_16)


  输入1，S2和S3的下一状态都是S2，输出也都是0；输入0，S2和S3的下一状态都是S0，输出也都是1，故S2和S3互为等价状态

- 米里模型：取决于状态和输入（见状态图eg）

  摩尔模型：只取决于状态（状态图无输入）
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/21f4290ef26e4d8380acc9c3c1ad339d.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_13,color_FFFFFF,t_70,g_se,x_16)


  混合摩尔和米里输出：见等价状态eg

- 序列识别器是一个识别特定比特流的时序电路，每当输入出现指定的序列时，输出一个特定值，比如1

  eg：识别1101

  第一状态是初始状态

  第二状态是识别到1

  第三状态是识别到1

  第四状态是识别到0

  第五状态是识别到1

  但第五状态又可作为下一个序列的开头1，所以第五个状态并到第二个状态
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/9f1525882ea34109aabeaf7addab50eb.png)


  若A状态的输入是0，则还是A状态；若B状态的输入为0，则回到A状态，若C状态的输入为1，则还是C状态；若D状态的输入为0，则回到A状态
![在这里插入图片描述](https://img-blog.csdnimg.cn/48ffba72a67147fab452f3dae151f8b8.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_17,color_FFFFFF,t_70,g_se,x_16)

  

  改为摩尔模型：则D不能回到B，需新加一个E状态，下一状态与B相同，输出不同
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/0738c40e3b0345568f6eae512b65d6d1.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_12,color_FFFFFF,t_70,g_se,x_16)


- 状态分配：

  分配法数量=状态数的阶乘

  不同的分配法成本不同

  - 计数顺序分配法：如按00，01，10，11的顺序分配A，B，C，D状态

  - 格雷码分配法：如按00，01，11，10的顺序分配A，B，C，D状态

  - One-Hot分配法：每个状态一个触发器，如按0001，0010，0100，1000的顺序分配A，B，C，D状态
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/a8108cdb1b2646bfab00dc989a4bfb24.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_18,color_FFFFFF,t_70,g_se,x_16)

    

    D3=~XY2

    D2=X(Y1+Y2)

    D1=X(Y0+Y3)

    D0=~X(Y0+Y1+Y3)

    Z=XY3

- 模n加法器：一个加法器对运算结果除以n得到的结果

  eg：2位时序模3累加器

  ![在这里插入图片描述](https://img-blog.csdnimg.cn/43bb4b4ba737432691a28d38cbe80bed.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_20,color_FFFFFF,t_70,g_se,x_16)


  D1 = Y1X1’X0’ + Y0X0 + Y1’X1 

  D0 = Y0X0’ + Y1X1 + Y1’Y0’X0 

- 有限状态机FSM：用于时序电路的基本数学模型

  包含I/O（输入、输出）和S（状态集合）以及f（下一状态函数），g（输出函数，由g分摩尔和米里

- 状态机图：处理大型设计

  因为0为默认，![在这里插入图片描述](https://img-blog.csdnimg.cn/504a1a33feb04450a4f69abdc725fa46.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_20,color_FFFFFF,t_70,g_se,x_16)
所以只需要标记出为1的表达式
  
  

- 可编程逻辑：

  - 以大容量生产，通过编程实现许多不同的小容量设计
  - 许多可编程逻辑器件现场可编程，可擦除和可重复编程

- 只读存储器ROM：固定的与阵列和可编程的或阵列

  - N根输入线，以及对N个输入进行译码的最小项2^N个。

  - M根输出线，对2^N个最小项做或运算，即最小项之和

    eg:
    ![在这里插入图片描述](https://img-blog.csdnimg.cn/52a2085e41cd49e8a7d69ff8d7d8456c.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_15,color_FFFFFF,t_70,g_se,x_16)


  F3 = D7 + D5 + D2 = A2 A1 A0 + A2 A1' A0 +A2’ A1 A0’ = A2 A0 + A2’ A1 A0’

  F2 = D7 + D0 = A2 A1 A0 + A2’ A1’ A0’ 

  F1 = D4 + D1 = A1 A1’ A0’ + A2’ A1’ A0

  F0 = D7 + D5 + D1 = A2 A0 + A1’ A0

- 可编程阵列逻辑PAL：可编程的与阵列和固定的或阵列

  - 缺点是输入到或门的可能更少

  - 可增加反相输出函数，可内部反馈实现多级电路

    ![在这里插入图片描述](https://img-blog.csdnimg.cn/abd6244deb0f46d1953c7d4a1d648eb6.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_14,color_FFFFFF,t_70,g_se,x_16)


    0(A),1(A'),2(B),3(B'),4(C),5(C'),6(D),7(D'),8(F1),9(F1')

    F1=C'+A'B'

    F2=A'BC'+AC+AB'

    F3=AD+BD+F1=AD+BD+C'+A'B'

    F4=AB+CD+F1'=AB+CD+C(A+B)=AB + CD + AC + BC 

- 可编程逻辑阵列PLA：可编程的与阵列和可编程的或阵列

  eg:
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/d4668e2cf021478cbb2eb9fe6a015158.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_20,color_FFFFFF,t_70,g_se,x_16)


  F1=AB+BC+AC

  F2=(AB+A'B')'=A'B+AB'

  异或门用于传递和取反：Axor1=A';Axor0=A

  如果F2不用异或门取反,则需要五个与门，而不是上图的4个

- 寄存器：二进制存储单元的集合，存储二进制向量。简单来说，就是由n个触发器组成。

  eg：2位寄存器

  ![在这里插入图片描述](https://img-blog.csdnimg.cn/ee4568e7863f4bdebdf696d2d1e8a44b.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_10,color_FFFFFF,t_70,g_se,x_16)


  有多少个状态?2^2 

  有多少个输入组合?输出组合? 都是2^2

  输出函数是什么?Y=A

  下一状态函数是什么?A(t+1)=In

  摩尔或米里?摩尔

- 寄存器设计

  随着n变大，状态数和输入输出组合变得很大，这时设计的方式：

  - 给寄存器加上事先设计好的电路：如寄存器的触发端接到一个递增电路，实现加法计数
  - 设计单个单元，然后组合成一个寄存器

- 寄存器存储

  - Load信号：

    屏蔽寄存器的时钟，控制寄存器的输出反馈到它的输入4

    控制寄存器存储和加载（1时从数据输入端加载值；0时时钟起作用，把值存储到寄存器中）

    eg：BCD计数器，1001时Load有效，把0000加载到寄存器

  - 含加载控制反馈的寄存器

    - 时钟不受影响

    - 加载信号选择是否加载输入值

    eg：
    ![在这里插入图片描述](https://img-blog.csdnimg.cn/455f92920996452babb76aaebd0442a6.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_20,color_FFFFFF,t_70,g_se,x_16)

    

    Load=0：加载寄存器内容（保持）

    Load=1：加载输入值（更新）

- 寄存器传输：移动或处理存储在寄存器里的数据

  - 基本部件：寄存器集+操作+操作的控制

  - 基本操作（微操作）:传输/算数运算(加、减、乘、除)/逻辑运算(与、或、异或、非)/移位

    - 移位微操作：注意”零填充“

  - 控制表达式：

    X K1 :  R1 <—— R1 + R2’ + 1

    如果XK1=1，则执行R1与R2的补码加法（即减法）

  - 传输结构：

    - 基于多路器的传输：多个输入由连接目的寄存器的多路器选择

      eg：

      K1:R0<——R1

      K2K1':R0<——R2

      ![在这里插入图片描述](https://img-blog.csdnimg.cn/d04b64ac73fb4001b7f0b692fad8d993.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_14,color_FFFFFF,t_70,g_se,x_16)


      ![在这里插入图片描述](https://img-blog.csdnimg.cn/3c4f2492433a4bc4880647db0052a7f9.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_20,color_FFFFFF,t_70,g_se,x_16)


      编码器加多路器：Ki：R0<——Ri

    - 基于专用多路器的传输：多路器连到每个寄存器的输入端，构成灵活的传输结构，能执行同时传输

      ![在这里插入图片描述](https://img-blog.csdnimg.cn/9258690e00034949b0a7fca21f7ea52a.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_12,color_FFFFFF,t_70,g_se,x_16)


    - 基于总线的传输：多个输入由一个共享的多路器驱动总线,把输出连到多个寄存器

      限制了同时传输，但节省成本

      ![在这里插入图片描述](https://img-blog.csdnimg.cn/315359f5f608455a9096bce66b6e41c9.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_11,color_FFFFFF,t_70,g_se,x_16)


    - 三态总线：多个输入由3态驱动器驱动,输出通过总线连多个寄存器

      用三态缓冲器取代多路器，进一步降低开销，减少连接数量

      ![在这里插入图片描述](https://img-blog.csdnimg.cn/2dc7673d4915482080d2410147765a7c.png)


    - 组合上述方法
  
  - 移位寄存器：
  
    - 数据串行输入输出：由一组D触发器连成一行
  
      ![在这里插入图片描述](https://img-blog.csdnimg.cn/f4ae6cc8ef8544c48c8a5f64e6c69adf.png)

  
    - 并行加载移位寄存器
  
      每级之间加一个多路器，数据就可以移位或加载
  
      - ![在这里插入图片描述](https://img-blog.csdnimg.cn/d4118f39803446b7a90544c3b98956cf.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_17,color_FFFFFF,t_70,g_se,x_16)

  
      SHIFT=1，分别读入IN，QA,右移
  
      SHIFT=0，读入D，加载

- 计数器：按特定状态顺序计数的时序电路

  - 行波计数器

    - 时钟连到最低位触发器的时钟端，其他触发器的时钟端则接上一触发器的输出
    - 不是同步，不稳定
    - 位数越多，向最高位输出变化的延时越高。如111变到000，第一位改变后，第二位改变，再是第三位改变。
    - 功耗低

    eg：
    ![在这里插入图片描述](https://img-blog.csdnimg.cn/885f211ec05c4d5daca5c56519476b58.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_10,color_FFFFFF,t_70,g_se,x_16)


    clock为上升沿时，A反相，实现0、1交叉出现

    当A反相后为1时，需要进位，则B的clock为上升沿，B反相

  - 同步计数器

    - 共同的时钟

    - 通过逻辑实现计数

      ![在这里插入图片描述](https://img-blog.csdnimg.cn/134d654e38084e7caac3e1425ed81cc3.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_19,color_FFFFFF,t_70,g_se,x_16)


    - 并行取代串行与门进位链

      与超前进位链类似，减少路径延时

      eg：图中异或门未画出

      ![在这里插入图片描述](https://img-blog.csdnimg.cn/c1513b2cbab949c5b1434775b338ab1d.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_11,color_FFFFFF,t_70,g_se,x_16)


    - 减法计数器

    - 并行加载计数器：Load信号有效，加载外部值

      ![在这里插入图片描述](https://img-blog.csdnimg.cn/3a6e192005764af3af4b1ad7bf79ced9.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_13,color_FFFFFF,t_70,g_se,x_16)


      Load=1：加载外部向量D

      Load=0，Count=1，计数；Load=0，Count=0，保持

      可用于构成模n计数器（检测n-1，此时Load有效加载0，同步清零)

      ![在这里插入图片描述](https://img-blog.csdnimg.cn/60295d1f7f534fe78fc984e0e0622ede.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_14,color_FFFFFF,t_70,g_se,x_16)


    - 自启动：计数器在经过几个周期的时钟后，可从无效状态变为有效状态

      ![在这里插入图片描述](https://img-blog.csdnimg.cn/a431f17b18404b31b1b712bc64b538b5.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_14,color_FFFFFF,t_70,g_se,x_16)


- 串行传输和微操作

  - 串行加法器：移位寄存器+全加器

    每次执行一位，结果放到A3，经过4次移位后，A变为A+B

    ![在这里插入图片描述](https://img-blog.csdnimg.cn/e950a4a6baf5475fb589963994c1d27c.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_14,color_FFFFFF,t_70,g_se,x_16)


- 存储器：能存储二进制信息的单元集合，包含必要的信息读和写的电路

  - 随机访问存储器（RAM）：可以从任意目标位置访问存储器单元来进行信息的输入输出，不同位置的单元访问时间一样长

  - 存储器地址：确定一个特定存储单元的位向量

  - 数据单元：

    bit（一位二进制数）

    byte（8位二进制信息序列）

    字（二进制信息被分组存储在存储器中，是信息访问的单元，2^n byte）

   ![在这里插入图片描述](https://img-blog.csdnimg.cn/c6aa35c9081e441d82c08c9b7cde1e33.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aSpWWXmtapTaXI=,size_14,color_FFFFFF,t_70,g_se,x_16)


    包含：n位数据输入和输出线，1位读和写线，k位地址线，译码成n=2^k进行寻址

- RAM集成电路

  - 按存储位置分类：

    静态：信息存储在锁存器中

    动态：信息作为充电电荷存储在电容中

  - 按供电分类

    易失：断电后信息丢失

    非易失：断电后信息不丢失

- 重合选择：一个译码器用来控制字选择，另一个译码器用来控制位选择，组成二维阵列模式

- 计算机体系结构：确定实现计算机硬件的高级描述

  - 执行微操作的数据通路
  - 控制数据通路操作的控制单元

- 数据通路：数据在功能部件之间传送的路径

  - 寄存器组
  - 对存储在寄存器中的数据执行的微操作
  - 控制单元接口

  设计原则：

  - 一组单独的寄存器组/寄存器文件（有公用访问资源的寄存器组）/上述的组合
  - 微操作的实现

- 算术逻辑单元ALU

  - 选择器+算数运算电路+逻辑运算电路

- 控制字：驱动数据通路中控制输入的信号

- 指令集体系结构ISA

  - 哈佛结构：分离指令和数据存储器，指令在一个时钟周期内执行完毕
  - 指令格式（3个）：寄存器、立即数、跳转和分支
    - 寄存器格式：指定源寄存器A、B+目的寄存器+操作码域
    - 立即数格式：操作数域+指定源寄存器+目的寄存器+操作码域
    - 跳转和分支格式：指定源寄存器+补码偏移量+操作码域
  - 助记符：指令的速记符
  - 指令译码器：在一个执行的时钟周期内根据指令各个字段的内容为数据通路提供控制字，来控制计算机的所有部分


