## 决策树
### 决策树思想
 ![123](https://pic2.zhimg.com/80/v2-39d109b46ea4f34d5efbf67edc11d57d_hd.png)
 
 （周志华老师西瓜书）
 
 分治思想：<br>
 *根据属性把数据集分成多组<br>
 *判断不同的数据点是否被完美区分(pure)<br>
 *不是：重复上面两步操作<br>
 *是的：收工<br>
 
### 熵 Entropy
怎么知道该选哪个属性去分开数据？<br>
在划分时不能随便选，我们希望每一步都得到最优划分属性。一般来说，在划分的过程我们希望决策树的分支节点包含的样本尽量属于同一类别，即纯度(Purity)越来越高<br>
1948年，克劳德·艾尔伍德·香农提出了“信息熵”概念。<br>
计算公式：<br>
![Entropy](https://img-blog.csdn.net/20161111043719435?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center)<br>
当H(x)的值越小，则结点的纯度就越高

### 信息增益 Information Gain
![Gain](https://img-blog.csdn.net/20161111044418126?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center)<br>
一般来说，信息增益越大，就意味着用属性这个属性来划分而获得的“纯度提示”越大，所以可以用信息增益作为标准来进行决策树的划分属性选择。<br>

### 常见算法
ID3算法：<br>
1）对当前样本集合，计算所有属性的信息增益； <br>
2）选择信息增益最⼤的属性作为测试属性， 把测试属性取值相同的样本划为同⼀个⼦样本集;<br>
3）若⼦样本集的类别属性只含有单个属性，则分⽀为叶⼦节点， 判断其属性值并标上相应的符号，然后返回调⽤处； 否则对⼦样本集递归调⽤本算法<br>

### 过拟合 Overfitting
ID3 的bug: <br>
1. 永远可以把N个数据分成100%纯洁的N组<br>
2.如果在『⽇期』这个条件下做分裂，就GG了<br>
举个栗子：<br>
现在我们拿到了肖爸爸的一组数据，让我们来预测肖爸爸某一天是否有课。<br><br>
属性有：日期、星期、肖爸爸早上什么时候起床、肖爸爸呆在家的时长、肖爸爸今天是否开车<br><br>
如果肖爸爸一个学期中每个星期星期几上课是一定的，如果我们拿这个"星期"属性来做划分就会过拟合<br>
如果下个学期肖爸爸每个星期星期几上课变了，拿上面的模型来就会出现明显的错误。<br>

### 避免过拟合
- 没必要的分裂不要整<br>
- 减枝Prune<br>

### 信息增益率
ID3的后继算法C4.5使用增益率（gain ratio）的信息增益扩充<br>
分裂信息：<br>
![Gain ratio](https://img-blog.csdn.net/20161111051507093?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center)<br>
增益率：<br>
![](https://img-blog.csdn.net/20161111051533131?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center)<br>

### 决策树的优劣
优势： <br>
- ⾮⿊盒 <br>
- 轻松去除⽆关属性 （Gain = 0） <br>
- Test起来很快 （O(depth)）<br><br>
劣势： <br>
- 只能线性分割数据<br> 
- 贪婪算法（可能找不到最好的树<br>
- 容易过拟合<br><br><br><br>

[titanic](https://www.kaggle.com/c/titanic/data)
