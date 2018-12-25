# 神经网络

## 神经元
![](https://img-blog.csdn.net/20161220192336053?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxMTgyNjQwNA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)<br>

"M-P 神经元模型"<br>

神经元接收到来自n个其它神经元传过来的输入信号，这些输入信号通过带权重的连接进行传递，神经元接收到的总输入值与神经元的阈值比较，通过激活函数处理产生输出。<br>


## 激活函数
![](https://img-blog.csdn.net/20161220192350037?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxMTgyNjQwNA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)<br>

阶跃函数是是神经元模型最理想的激活函数，但是它具有不连续、不光滑的特点，因此常把Sigmoid函数作为神经元的激活函数。<br>

神经网络就是由多个神经元连接而成的，每个神经元都可以看作一个函数，神经网络可以看成用很多个函数相互嵌套而成的。<br>

## 感知机与多层网络
![](https://images2015.cnblogs.com/blog/673793/201512/673793-20151221151959015-1876891081.jpg)<br>
在“感知器”中，有两个层次。分别是输入层和输出层。输入层里的“输入单元”只负责传输数据，不做计算。输出层里的“输出单元”则需要对前面一层的输入进行计算。<br>
感知机能实现简单的逻辑与、或、非运算。而这些问题都是线性可分的。若两类模式是线性可分的，即存在一个超平面可以将他们分开，则感知机的学习过程一定会收敛。而对于异或这样简单的非线性可分的问题，感知机不能完成。<br>
![](https://img-blog.csdn.net/20151005182955041)<br>

![](https://pic1.zhimg.com/80/v2-4c7fd5b9b5ebf7ef498e4dad314d7ec4_hd.jpg)<br><br>


解决非线性可分问题需要用到多层功能神经元来解决<br>
![](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR1ABuIf0lnJnR-GMydHv7vFYa3LMN-fzIcyxMOpNU7rDVu-DXX)<br>

[tensorflow playground](https://playground.tensorflow.org/#activation=tanh&batchSize=10&dataset=circle&regDataset=reg-plane&learningRate=0.03&regularizationRate=0&noise=0&networkShape=4,2&seed=0.26176&showTestData=false&discretize=false&percTrainData=50&x=true&y=true&xTimesY=false&xSquared=false&ySquared=false&cosX=false&sinX=false&cosY=false&sinY=false&collectStats=false&problem=classification&initZero=false&hideText=false)<br>

## 误差逆传播算法 BP
![](http://images.cnitblog.com/blog/571227/201411/231429324377605.png)
