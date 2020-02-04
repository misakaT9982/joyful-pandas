# Joyful-Pandas

#### 一、写作初衷

在使用Pandas之前，几乎所有的大型表格处理问题都是用xlrt和python循环实现，虽然这已经几乎能完成一切的需求，但其缺点也显而易见，其一就是速度问题，其二就是代码的复用性几乎为0。

曾经也尝试过去零星地学Pandas，但不得不说这个包实在太过庞大，每次使用总觉得盲人摸象，每个函数的参数也很多，学习的路线并不是十分平缓。如果你刚刚手上使用Pandas，那么在碎片的学习过程中，报错是常常发生的事，并且很难修（因为不理解内部的操作），即使修好了下次又不会，令人有些沮丧。

上个学期（2019秋季），我偶然找到了一本完全关于Pandas的书，Theodore Petrou所著的Pandas Cookbook，现在可在网上下到pdf，不过现在还没有中文版。寒假开始后，立即快速地过了一遍，发现之前很多搞不清的概念得到了较好的解答，逐步地再对着User Guide一字一句查看，最后总是建立了大的一些宏观概念。

最关键的一步，我想是通读了官方User Guide的绝大部分内容，这可能是非常重要的一个台阶，毕竟官方的教程总是会告诉你重点在哪里。因此，经过了一段时间的思考，结合了Wes Mckinney（Pandas之父）的[Python for Data Analysis](<http://93.174.95.29/_ads/A3AD6E6B2504B95EC39A6C57D465BA5D>)、先前提到的[Pandas Cookbook](<http://93.174.95.29/_ads/23950B4446ABB5DD27168D6B0FB2C8DB>)和官方的[User Guide](<https://pandas.pydata.org/pandas-docs/version/1.0.0/user_guide/index.html>)，由此想按照自己的思路编一套关于Pandas的教程，完整梳理Pandas的主线内容，杜绝浅尝辄止，保证涉及每个部分的核心概念和函数。最后，希望达到的境界自然是“所写所得即所想”，这大概需要更多的实践，也是努力实现的目标方向。

关于项目的名字，我想原先使用Pandas时非常的痛苦（Painful），那现在是时候转变为“Joyful-Pandas”了！

#### 二、编排思路

本项目共有十一章，可以大致分为5个板块：

1、拿到数据必然先要读取它，分析完了数据必然是要保存它，读取了数据之后，我们面对了怎样的对象（Series? of Dataframe?）是第一重要的课题，因此了解序列和数据框的常规操作及其组件（component）便是必须涉及的内容。

2、对于一个DataFrame而言，果一个操作使得它的元素信息减少了，那就对应了索引，即第二章的内容；如果这个操作使得数据的信息被充分地使用，那有两种可能，第一是数据被分组，从组内提取了关键的信息，第二就是数据呈现的结构或形态上的变化，使得我们更容易地能够地进一步处理数据，这两者分别对应了第三章与第四章的内容；最终如果一个操作使得原本不属于这个数据框的信息被加入了进来，那往往是涉及到了合并操作，对应了第五章的内容。从数据信息增减的角度，拆解成了3个板块，4个章节，几乎串联其了官方文档关于数据框操作的全部内容，我想这样的安排是合适的。

3、如果说前面我们关心了序列和数据框这两种容器的结构和操作，那么下面就要关心其中的元素。其中，将涉及四类特殊的数据类型：缺失型数据、文本型数据、分类型数据和时间序列型数据，分别对应了6-9章的内容。

4、在第10章中，我们将涉及Pandas中的可视化，了解如何实现Matplotlib和Pandas之间的无缝衔接。

5、正如前面所说，Pandas的学习往往是任务驱动型，一个操作或者某个方法，不去使用自然会很快地忘记（除非你天赋异禀！），因此我在2-9章都会添加“问题和练习”的部分。其中，问题中出现的往往是对于教程中某个细节的深入，或者在这一个章节中重要的函数，希望你能够查阅相关资料阅读以解决问题；而练习部分包含了两个综合题，分别是两个不同的案例，相当于对前面所学知识的考察与综合运用，虽然并不是非常复杂，但是想要全部完成，的确是要动一些脑筋才行。最终，在第11章中会添加若干个我曾经遇到过但解决方案复杂，或者我想到的某一个一时半会儿还没有解决办法的问题，具有一定的挑战性，如果有较好的解决方案，欢迎交流分享，谢谢：）

6、基于完整性，我也为所有的练习编写了参考答案，当然它可能不是最好的（也许永远没有最好的），但是不失为一种提示与策略。

最后，祝你有所收获！

#### 三、内容导航

| 章节                                                         | 小节                                                         | 内容                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| [第1章 Pandas基础]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC1%E7%AB%A0%20Pandas%E5%9F%BA%E7%A1%80.ipynb#%E7%AC%AC1%E7%AB%A0-Pandas%E5%9F%BA%E7%A1%80>) | [一、文件读取与写入]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC1%E7%AB%A0%20Pandas%E5%9F%BA%E7%A1%80.ipynb#%E4%B8%80%E3%80%81%E6%96%87%E4%BB%B6%E8%AF%BB%E5%8F%96%E4%B8%8E%E5%86%99%E5%85%A5>) | [1. 读取]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC1%E7%AB%A0%20Pandas%E5%9F%BA%E7%A1%80.ipynb#1.-%E8%AF%BB%E5%8F%96>) |
|                                                              |                                                              | [2. 写入]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC1%E7%AB%A0%20Pandas%E5%9F%BA%E7%A1%80.ipynb#2.-%E5%86%99%E5%85%A5>) |
|                                                              | [二、基本数据结构]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC1%E7%AB%A0%20Pandas%E5%9F%BA%E7%A1%80.ipynb#%E4%BA%8C%E3%80%81%E5%9F%BA%E6%9C%AC%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84>) | [1. Series]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC1%E7%AB%A0%20Pandas%E5%9F%BA%E7%A1%80.ipynb#1.-Series>) |
|                                                              |                                                              | [2. DataFrame]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC1%E7%AB%A0%20Pandas%E5%9F%BA%E7%A1%80.ipynb#2.-DataFrame>) |
|                                                              | [三、常用基本函数]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC1%E7%AB%A0%20Pandas%E5%9F%BA%E7%A1%80.ipynb#%E4%B8%89%E3%80%81%E5%B8%B8%E7%94%A8%E5%9F%BA%E6%9C%AC%E5%87%BD%E6%95%B0>) | [1. head和tail]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC1%E7%AB%A0%20Pandas%E5%9F%BA%E7%A1%80.ipynb#1.-head%E5%92%8Ctail>) |
|                                                              |                                                              | [2. unique/nunique/count/value_counts]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC1%E7%AB%A0%20Pandas%E5%9F%BA%E7%A1%80.ipynb#2.-unique/nunique/count/value_counts>) |
|                                                              |                                                              | [3. describe和info](  <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC1%E7%AB%A0%20Pandas%E5%9F%BA%E7%A1%80.ipynb#3.-describe%E5%92%8Cinfo>) |
|                                                              |                                                              | [4. idxmax和nlargest]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC1%E7%AB%A0%20Pandas%E5%9F%BA%E7%A1%80.ipynb#4.-idxmax%E5%92%8Cnlargest>) |
|                                                              |                                                              | [5. clip和replace]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC1%E7%AB%A0%20Pandas%E5%9F%BA%E7%A1%80.ipynb#5.-clip%E5%92%8Creplace>) |
|                                                              |                                                              | [6. apply函数](  <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC1%E7%AB%A0%20Pandas%E5%9F%BA%E7%A1%80.ipynb#6.-apply%E5%87%BD%E6%95%B0>) |
|                                                              | [四、排序]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC1%E7%AB%A0%20Pandas%E5%9F%BA%E7%A1%80.ipynb#%E5%9B%9B%E3%80%81%E6%8E%92%E5%BA%8F>) | [1. 索引排序]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC1%E7%AB%A0%20Pandas%E5%9F%BA%E7%A1%80.ipynb#1.-%E7%B4%A2%E5%BC%95%E6%8E%92%E5%BA%8F>) |
|                                                              |                                                              | [2. 值排序]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC1%E7%AB%A0%20Pandas%E5%9F%BA%E7%A1%80.ipynb#2.-%E5%80%BC%E6%8E%92%E5%BA%8F>) |
| [第2章 索引]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#%E7%AC%AC2%E7%AB%A0-%E7%B4%A2%E5%BC%95>) | [一、单级索引]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#%E4%B8%80%E3%80%81%E5%8D%95%E7%BA%A7%E7%B4%A2%E5%BC%95>) | [1. loc方法、iloc方法、[]操作符]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#1.-loc%E6%96%B9%E6%B3%95%E3%80%81iloc%E6%96%B9%E6%B3%95%E3%80%81[]%E6%93%8D%E4%BD%9C%E7%AC%A6>) |
|                                                              |                                                              | [2. 布尔索引]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#2.-%E5%B8%83%E5%B0%94%E7%B4%A2%E5%BC%95>) |
|                                                              |                                                              | [3. 快速标量索引]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#3.-%E5%BF%AB%E9%80%9F%E6%A0%87%E9%87%8F%E7%B4%A2%E5%BC%95>) |
|                                                              |                                                              | [4. 区间索引]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#4.-%E5%8C%BA%E9%97%B4%E7%B4%A2%E5%BC%95>) |
|                                                              | [二、多级索引]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#%E4%BA%8C%E3%80%81%E5%A4%9A%E7%BA%A7%E7%B4%A2%E5%BC%95>) | [1. 创建多级索引]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#1.-%E5%88%9B%E5%BB%BA%E5%A4%9A%E7%BA%A7%E7%B4%A2%E5%BC%95>) |
|                                                              |                                                              | [2. 多层索引切片](  <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#2.-%E5%A4%9A%E5%B1%82%E7%B4%A2%E5%BC%95%E5%88%87%E7%89%87>) |
|                                                              |                                                              | [3. 多层索引中的slice对象](  <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#3.-%E5%A4%9A%E5%B1%82%E7%B4%A2%E5%BC%95%E4%B8%AD%E7%9A%84slice%E5%AF%B9%E8%B1%A1>) |
|                                                              |                                                              | [4. 索引层的交换](  <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#4.-%E7%B4%A2%E5%BC%95%E5%B1%82%E7%9A%84%E4%BA%A4%E6%8D%A2>) |
|                                                              | [三、索引设定]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#%E4%B8%89%E3%80%81%E7%B4%A2%E5%BC%95%E8%AE%BE%E5%AE%9A>) | [1. index_col参数]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#1.-index_col%E5%8F%82%E6%95%B0>) |
|                                                              |                                                              | [2. reindex和reindex_like](  <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#2.-reindex%E5%92%8Creindex_like>) |
|                                                              |                                                              | [3. set_index和reset_index](  <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#3.-set_index%E5%92%8Creset_index>) |
|                                                              |                                                              | [4. rename_axis和rename](  <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#4.-rename_axis%E5%92%8Crename>) |
|                                                              | [四、常用索引型函数](  <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#%E5%9B%9B%E3%80%81%E5%B8%B8%E7%94%A8%E7%B4%A2%E5%BC%95%E5%9E%8B%E5%87%BD%E6%95%B0>) | [1. where函数]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#4.-rename_axis%E5%92%8Crename>) |
|                                                              |                                                              | [2. mask函数]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#2.-mask%E5%87%BD%E6%95%B0>) |
|                                                              |                                                              | [3. query函数]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#3.-query%E5%87%BD%E6%95%B0>) |
|                                                              | [五、重复元素处理]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#%E4%BA%94%E3%80%81%E9%87%8D%E5%A4%8D%E5%85%83%E7%B4%A0%E5%A4%84%E7%90%86>) | [1. duplicated方法]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#1.-duplicated%E6%96%B9%E6%B3%95>) |
|                                                              |                                                              | [2. drop_duplicates方法]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#2.-drop_duplicates%E6%96%B9%E6%B3%95>) |
|                                                              | [六、抽样函数]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#%E5%85%AD%E3%80%81%E6%8A%BD%E6%A0%B7%E5%87%BD%E6%95%B0>) | [抽样函数]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#%E5%85%AD%E3%80%81%E6%8A%BD%E6%A0%B7%E5%87%BD%E6%95%B0>) |
|                                                              | [七、问题与练习]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#%E4%B8%83%E3%80%81%E9%97%AE%E9%A2%98%E4%B8%8E%E7%BB%83%E4%B9%A0>) | [问题]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#%E3%80%90%E9%97%AE%E9%A2%98%E4%B8%80%E3%80%91-%E5%A6%82%E4%BD%95%E6%9B%B4%E6%94%B9%E5%88%97%E6%88%96%E8%A1%8C%E7%9A%84%E9%A1%BA%E5%BA%8F%EF%BC%9F>) |
|                                                              |                                                              | [练习一]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#%E3%80%90%E7%BB%83%E4%B9%A0%E4%B8%80%E3%80%91-%E7%8E%B0%E6%9C%89%E4%B8%80%E4%BB%BD%E5%85%B3%E4%BA%8EUFO%E7%9A%84%E6%95%B0%E6%8D%AE%E9%9B%86%EF%BC%8C%E8%AF%B7%E8%A7%A3%E5%86%B3%E4%B8%8B%E5%88%97%E9%97%AE%E9%A2%98%EF%BC%9A>) |
|                                                              |                                                              | [练习二]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC2%E7%AB%A0%20%E7%B4%A2%E5%BC%95.ipynb#%E3%80%90%E7%BB%83%E4%B9%A0%E4%BA%8C%E3%80%91-%E7%8E%B0%E6%9C%89%E4%B8%80%E4%BB%BD%E5%85%B3%E4%BA%8E%E5%8F%A3%E8%A2%8B%E5%A6%96%E6%80%AA%E7%9A%84%E6%95%B0%E6%8D%AE%E9%9B%86%EF%BC%8C%E8%AF%B7%E8%A7%A3%E5%86%B3%E4%B8%8B%E5%88%97%E9%97%AE%E9%A2%98%EF%BC%9A>) |
| [第3章 分组]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC3%E7%AB%A0%20%E5%88%86%E7%BB%84.ipynb#%E7%AC%AC3%E7%AB%A0-%E5%88%86%E7%BB%84>) | [一、SAC过程]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC3%E7%AB%A0%20%E5%88%86%E7%BB%84.ipynb#%E4%B8%80%E3%80%81SAC%E8%BF%87%E7%A8%8B>) | [1. 内涵]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC3%E7%AB%A0%20%E5%88%86%E7%BB%84.ipynb#1.-%E5%86%85%E6%B6%B5>) |
|                                                              |                                                              | [2. apply过程]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC3%E7%AB%A0%20%E5%88%86%E7%BB%84.ipynb#2.-apply%E8%BF%87%E7%A8%8B>) |
|                                                              | [二、groupby函数]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC3%E7%AB%A0%20%E5%88%86%E7%BB%84.ipynb#%E4%BA%8C%E3%80%81groupby%E5%87%BD%E6%95%B0>) | [1. 分组函数的基本内容]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC3%E7%AB%A0%20%E5%88%86%E7%BB%84.ipynb#1.-%E5%88%86%E7%BB%84%E5%87%BD%E6%95%B0%E7%9A%84%E5%9F%BA%E6%9C%AC%E5%86%85%E5%AE%B9%EF%BC%9A>) |
|                                                              |                                                              | [2. groupby对象的特点]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC3%E7%AB%A0%20%E5%88%86%E7%BB%84.ipynb#2.-groupby%E5%AF%B9%E8%B1%A1%E7%9A%84%E7%89%B9%E7%82%B9>) |
|                                                              | [三、聚合、过滤和变换]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC3%E7%AB%A0%20%E5%88%86%E7%BB%84.ipynb#%E4%B8%89%E3%80%81%E8%81%9A%E5%90%88%E3%80%81%E8%BF%87%E6%BB%A4%E5%92%8C%E5%8F%98%E6%8D%A2>) | [1. 聚合（Aggregation）]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC3%E7%AB%A0%20%E5%88%86%E7%BB%84.ipynb#1.-%E8%81%9A%E5%90%88%EF%BC%88Aggregation%EF%BC%89>) |
|                                                              |                                                              | [2. 过滤（Filteration）]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC3%E7%AB%A0%20%E5%88%86%E7%BB%84.ipynb#2.-%E8%BF%87%E6%BB%A4%EF%BC%88Filteration%EF%BC%89>) |
|                                                              |                                                              | [3. 变换（Transformation）]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC3%E7%AB%A0%20%E5%88%86%E7%BB%84.ipynb#3.-%E5%8F%98%E6%8D%A2%EF%BC%88Transformation%EF%BC%89>) |
|                                                              | [四、apply函数]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC3%E7%AB%A0%20%E5%88%86%E7%BB%84.ipynb#%E5%9B%9B%E3%80%81apply%E5%87%BD%E6%95%B0>) | [1. apply函数的灵活性]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC3%E7%AB%A0%20%E5%88%86%E7%BB%84.ipynb#1.-apply%E5%87%BD%E6%95%B0%E7%9A%84%E7%81%B5%E6%B4%BB%E6%80%A7>) |
|                                                              |                                                              | [2. 用apply同时统计多个指标]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC3%E7%AB%A0%20%E5%88%86%E7%BB%84.ipynb#2.-%E7%94%A8apply%E5%90%8C%E6%97%B6%E7%BB%9F%E8%AE%A1%E5%A4%9A%E4%B8%AA%E6%8C%87%E6%A0%87>) |
|                                                              | [五、问题与练习]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC3%E7%AB%A0%20%E5%88%86%E7%BB%84.ipynb#%E4%BA%94%E3%80%81%E9%97%AE%E9%A2%98%E4%B8%8E%E7%BB%83%E4%B9%A0>) | [问题]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC3%E7%AB%A0%20%E5%88%86%E7%BB%84.ipynb#%E3%80%90%E9%97%AE%E9%A2%98%E4%B8%80%E3%80%91-rolling%E5%92%8Cexpanding%E6%96%B9%E6%B3%95%E4%BB%8E%E5%8E%9F%E7%90%86%E4%B8%8A%E8%AF%B4%E9%83%BD%E6%98%AF%E4%B8%80%E7%A7%8Dtransform%E6%96%B9%E6%B3%95%EF%BC%8C%E8%AF%B7%E9%97%AE%E5%AE%83%E4%BB%AC%E6%9C%89%E4%BB%80%E4%B9%88%E5%8C%BA%E5%88%AB%EF%BC%9F>) |
|                                                              |                                                              | [练习一]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC3%E7%AB%A0%20%E5%88%86%E7%BB%84.ipynb#%E3%80%90%E7%BB%83%E4%B9%A0%E4%B8%80%E3%80%91%EF%BC%9A-%E7%8E%B0%E6%9C%89%E4%B8%80%E4%BB%BD%E5%85%B3%E4%BA%8Ediamonds%E7%9A%84%E6%95%B0%E6%8D%AE%E9%9B%86%EF%BC%8C%E5%88%97%E5%88%86%E5%88%AB%E8%AE%B0%E5%BD%95%E4%BA%86%E5%85%8B%E6%8B%89%E6%95%B0%E3%80%81%E9%A2%9C%E8%89%B2%E3%80%81%E5%BC%80%E9%87%87%E6%B7%B1%E5%BA%A6%E3%80%81%E4%BB%B7%E6%A0%BC%EF%BC%8C%E8%AF%B7%E8%A7%A3%E5%86%B3%E4%B8%8B%E5%88%97%E9%97%AE%E9%A2%98%EF%BC%9A>) |
|                                                              |                                                              | [练习二]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC3%E7%AB%A0%20%E5%88%86%E7%BB%84.ipynb#%E3%80%90%E7%BB%83%E4%B9%A0%E4%BA%8C%E3%80%91%EF%BC%9A%E6%9C%89%E4%B8%80%E4%BB%BD%E5%85%B3%E4%BA%8E%E7%BE%8E%E5%9B%BD10%E5%B9%B4%E8%87%B317%E5%B9%B4%E7%9A%84%E9%9D%9E%E6%B3%95%E8%8D%AF%E7%89%A9%E6%95%B0%E6%8D%AE%E9%9B%86%EF%BC%8C%E5%88%97%E5%88%86%E5%88%AB%E8%AE%B0%E5%BD%95%E4%BA%86%E5%B9%B4%E4%BB%BD%E3%80%81%E5%B7%9E%EF%BC%885%E4%B8%AA%EF%BC%89%E3%80%81%E5%8E%BF%E3%80%81%E8%8D%AF%E7%89%A9%E7%B1%BB%E5%9E%8B%E3%80%81%E6%8A%A5%E5%91%8A%E6%95%B0%E9%87%8F%EF%BC%8C%E8%AF%B7%E8%A7%A3%E5%86%B3%E4%B8%8B%E5%88%97%E9%97%AE%E9%A2%98%EF%BC%9A>) |
| [第4章 变形]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC4%E7%AB%A0%20%E5%8F%98%E5%BD%A2.ipynb#%E7%AC%AC4%E7%AB%A0-%E5%8F%98%E5%BD%A2>) | [一、透视表]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC4%E7%AB%A0%20%E5%8F%98%E5%BD%A2.ipynb#%E4%B8%80%E3%80%81%E9%80%8F%E8%A7%86%E8%A1%A8>) | [1. pivot]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC4%E7%AB%A0%20%E5%8F%98%E5%BD%A2.ipynb#1.-pivot>) |
|                                                              |                                                              | [2. pivot_table]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC4%E7%AB%A0%20%E5%8F%98%E5%BD%A2.ipynb#2.-pivot_table>) |
|                                                              |                                                              | [3. crosstab（交叉表）]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC4%E7%AB%A0%20%E5%8F%98%E5%BD%A2.ipynb#3.-crosstab%EF%BC%88%E4%BA%A4%E5%8F%89%E8%A1%A8%EF%BC%89>) |
|                                                              | [二、其他变形方法]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC4%E7%AB%A0%20%E5%8F%98%E5%BD%A2.ipynb#%E4%BA%8C%E3%80%81%E5%85%B6%E4%BB%96%E5%8F%98%E5%BD%A2%E6%96%B9%E6%B3%95>) | [1. melt]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC4%E7%AB%A0%20%E5%8F%98%E5%BD%A2.ipynb#1.-melt>) |
|                                                              |                                                              | [2. 压缩与展开]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC4%E7%AB%A0%20%E5%8F%98%E5%BD%A2.ipynb#2.-%E5%8E%8B%E7%BC%A9%E4%B8%8E%E5%B1%95%E5%BC%80>) |
|                                                              | [三、哑变量与因子化]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC4%E7%AB%A0%20%E5%8F%98%E5%BD%A2.ipynb#%E4%B8%89%E3%80%81%E5%93%91%E5%8F%98%E9%87%8F%E4%B8%8E%E5%9B%A0%E5%AD%90%E5%8C%96>) | [1. Dummy Variable（哑变量）]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC4%E7%AB%A0%20%E5%8F%98%E5%BD%A2.ipynb#1.-Dummy-Variable%EF%BC%88%E5%93%91%E5%8F%98%E9%87%8F%EF%BC%89>) |
|                                                              |                                                              | [2. factorize方法]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC4%E7%AB%A0%20%E5%8F%98%E5%BD%A2.ipynb#2.-factorize%E6%96%B9%E6%B3%95>) |
|                                                              | [四、问题与练习]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC4%E7%AB%A0%20%E5%8F%98%E5%BD%A2.ipynb#%E5%9B%9B%E3%80%81%E9%97%AE%E9%A2%98%E4%B8%8E%E7%BB%83%E4%B9%A0>) | [问题]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC4%E7%AB%A0%20%E5%8F%98%E5%BD%A2.ipynb#%E3%80%90%E9%97%AE%E9%A2%98%E4%B8%80%E3%80%91-%E4%B8%8A%E9%9D%A2%E6%8F%90%E5%88%B0%E4%BA%86%E8%AE%B8%E5%A4%9A%E5%8F%98%E5%BD%A2%E5%87%BD%E6%95%B0%EF%BC%8C%E5%A6%82melt/crosstab/pivot/pivot_table/stack/unstack%E5%87%BD%E6%95%B0%EF%BC%8C%E8%AF%B7%E6%80%BB%E7%BB%93%E5%AE%83%E4%BB%AC%E5%90%84%E8%87%AA%E7%9A%84%E4%BD%BF%E7%94%A8%E7%89%B9%E7%82%B9%E3%80%82>) |
|                                                              |                                                              | [练习一]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC4%E7%AB%A0%20%E5%8F%98%E5%BD%A2.ipynb#%E3%80%90%E7%BB%83%E4%B9%A0%E4%B8%80%E3%80%91-%E7%BB%A7%E7%BB%AD%E4%BD%BF%E7%94%A8%E4%B8%8A%E4%B8%80%E7%AB%A0%E7%9A%84%E8%8D%AF%E7%89%A9%E6%95%B0%E6%8D%AE%E9%9B%86%EF%BC%9A>) |
|                                                              |                                                              | [练习二]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC4%E7%AB%A0%20%E5%8F%98%E5%BD%A2.ipynb#%E3%80%90%E7%BB%83%E4%B9%A0%E4%BA%8C%E3%80%91-%E7%8E%B0%E6%9C%89%E4%B8%80%E4%BB%BD%E5%85%B3%E4%BA%8E%E6%9F%90%E5%9C%B0%E5%8C%BA%E5%9C%B0%E9%9C%87%E6%83%85%E5%86%B5%E7%9A%84%E6%95%B0%E6%8D%AE%E9%9B%86%EF%BC%8C%E8%AF%B7%E8%A7%A3%E5%86%B3%E5%A6%82%E4%B8%8B%E9%97%AE%E9%A2%98%EF%BC%9A>) |
| [第5章 合并]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC5%E7%AB%A0%20%E5%90%88%E5%B9%B6.ipynb#%E7%AC%AC5%E7%AB%A0-%E5%90%88%E5%B9%B6>) | [一、append与assign]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC5%E7%AB%A0%20%E5%90%88%E5%B9%B6.ipynb#%E4%B8%80%E3%80%81append%E4%B8%8Eassign>) | [1. append方法]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC5%E7%AB%A0%20%E5%90%88%E5%B9%B6.ipynb#1.-append%E6%96%B9%E6%B3%95>) |
|                                                              |                                                              | [2. assign方法]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC5%E7%AB%A0%20%E5%90%88%E5%B9%B6.ipynb#2.-assign%E6%96%B9%E6%B3%95>) |
|                                                              | [二、combine与update]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC5%E7%AB%A0%20%E5%90%88%E5%B9%B6.ipynb#%E4%BA%8C%E3%80%81combine%E4%B8%8Eupdate>) | [1. comine方法]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC5%E7%AB%A0%20%E5%90%88%E5%B9%B6.ipynb#1.-comine%E6%96%B9%E6%B3%95>) |
|                                                              |                                                              | [2. update方法]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC5%E7%AB%A0%20%E5%90%88%E5%B9%B6.ipynb#2.-update%E6%96%B9%E6%B3%95>) |
|                                                              | [三、concat方法]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC5%E7%AB%A0%20%E5%90%88%E5%B9%B6.ipynb#%E4%B8%89%E3%80%81concat%E6%96%B9%E6%B3%95>) | [concat方法]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC5%E7%AB%A0%20%E5%90%88%E5%B9%B6.ipynb#%E4%B8%89%E3%80%81concat%E6%96%B9%E6%B3%95>) |
|                                                              | [四、merge与join]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC5%E7%AB%A0%20%E5%90%88%E5%B9%B6.ipynb#%E5%9B%9B%E3%80%81merge%E4%B8%8Ejoin>) | [1. merge函数]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC5%E7%AB%A0%20%E5%90%88%E5%B9%B6.ipynb#1.-merge%E5%87%BD%E6%95%B0>) |
|                                                              |                                                              | [2. join函数]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC5%E7%AB%A0%20%E5%90%88%E5%B9%B6.ipynb#2.-join%E5%87%BD%E6%95%B0>) |
|                                                              | [五、问题与练习]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC5%E7%AB%A0%20%E5%90%88%E5%B9%B6.ipynb#%E4%BA%94%E3%80%81%E9%97%AE%E9%A2%98%E4%B8%8E%E7%BB%83%E4%B9%A0>) | [问题]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC5%E7%AB%A0%20%E5%90%88%E5%B9%B6.ipynb#%E3%80%90%E9%97%AE%E9%A2%98%E4%B8%80%E3%80%91-%E8%AF%B7%E6%80%9D%E8%80%83%E4%BB%80%E4%B9%88%E6%98%AFappend/assign/combine/update/concat/merge/join%E5%90%84%E8%87%AA%E6%9C%80%E9%80%82%E5%90%88%E4%BD%BF%E7%94%A8%E7%9A%84%E5%9C%BA%E6%99%AF%EF%BC%8C%E5%B9%B6%E4%B8%BE%E5%87%BA%E7%9B%B8%E5%BA%94%E7%9A%84%E4%BE%8B%E5%AD%90%E3%80%82>) |
|                                                              |                                                              | [练习一]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC5%E7%AB%A0%20%E5%90%88%E5%B9%B6.ipynb#%E3%80%90%E7%BB%83%E4%B9%A0%E4%B8%80%E3%80%91%E6%9C%892%E5%BC%A0%E5%85%AC%E5%8F%B8%E7%9A%84%E5%91%98%E5%B7%A5%E4%BF%A1%E6%81%AF%E8%A1%A8%EF%BC%8C%E6%AF%8F%E4%B8%AA%E5%85%AC%E5%8F%B8%E5%85%B1%E6%9C%8916%E5%90%8D%E5%91%98%E5%B7%A5%EF%BC%8C%E5%85%B1%E6%9C%89%E4%BA%94%E4%B8%AA%E5%85%AC%E5%8F%B8%EF%BC%8C%E8%AF%B7%E8%A7%A3%E5%86%B3%E5%A6%82%E4%B8%8B%E9%97%AE%E9%A2%98%EF%BC%9A>) |
|                                                              |                                                              | [练习二]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC5%E7%AB%A0%20%E5%90%88%E5%B9%B6.ipynb#%E3%80%90%E7%BB%83%E4%B9%A0%E4%BA%8C%E3%80%91%E6%9C%892%E5%BC%A0%E8%AF%BE%E7%A8%8B%E7%9A%84%E5%88%86%E6%95%B0%E8%A1%A8%EF%BC%88%E5%88%86%E6%95%B0%E9%9A%8F%E6%9C%BA%E7%94%9F%E6%88%90%EF%BC%89%EF%BC%8C%E4%BD%86%E4%B8%93%E4%B8%9A%E8%AF%BE%EF%BC%88%E5%AD%A6%E7%A7%91%E5%9F%BA%E7%A1%80%E8%AF%BE%E3%80%81%E4%B8%93%E4%B8%9A%E5%BF%85%E4%BF%AE%E8%AF%BE%E3%80%81%E4%B8%93%E4%B8%9A%E9%80%89%E4%BF%AE%E8%AF%BE%EF%BC%89%E4%B8%8E%E5%85%B6%E4%BB%96%E8%AF%BE%E7%A8%8B%E6%B7%B7%E5%9C%A8%E4%B8%80%E8%B5%B7%EF%BC%8C%E8%AF%B7%E8%A7%A3%E5%86%B3%E5%A6%82%E4%B8%8B%E9%97%AE%E9%A2%98%EF%BC%9A>) |
| [第6章 缺失数据]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC6%E7%AB%A0%20%E7%BC%BA%E5%A4%B1%E6%95%B0%E6%8D%AE.ipynb#%E7%AC%AC6%E7%AB%A0-%E7%BC%BA%E5%A4%B1%E6%95%B0%E6%8D%AE>) | [一、缺失观测及其类型]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC6%E7%AB%A0%20%E7%BC%BA%E5%A4%B1%E6%95%B0%E6%8D%AE.ipynb#%E4%B8%80%E3%80%81%E7%BC%BA%E5%A4%B1%E8%A7%82%E6%B5%8B%E5%8F%8A%E5%85%B6%E7%B1%BB%E5%9E%8B>) | [1. 了解缺失信息]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC6%E7%AB%A0%20%E7%BC%BA%E5%A4%B1%E6%95%B0%E6%8D%AE.ipynb#1.-%E4%BA%86%E8%A7%A3%E7%BC%BA%E5%A4%B1%E4%BF%A1%E6%81%AF>) |
|                                                              |                                                              | [2. 三种缺失符号](  <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC6%E7%AB%A0%20%E7%BC%BA%E5%A4%B1%E6%95%B0%E6%8D%AE.ipynb#2.-%E4%B8%89%E7%A7%8D%E7%BC%BA%E5%A4%B1%E7%AC%A6%E5%8F%B7>) |
|                                                              |                                                              | [3. Nullable类型与NA符号]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC6%E7%AB%A0%20%E7%BC%BA%E5%A4%B1%E6%95%B0%E6%8D%AE.ipynb#3.-Nullable%E7%B1%BB%E5%9E%8B%E4%B8%8ENA%E7%AC%A6%E5%8F%B7>) |
|                                                              |                                                              | [4. NA的特性]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC6%E7%AB%A0%20%E7%BC%BA%E5%A4%B1%E6%95%B0%E6%8D%AE.ipynb#4.-NA%E7%9A%84%E7%89%B9%E6%80%A7>) |
|                                                              |                                                              | [5. convert_dtypes方法]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC6%E7%AB%A0%20%E7%BC%BA%E5%A4%B1%E6%95%B0%E6%8D%AE.ipynb#5.--convert_dtypes%E6%96%B9%E6%B3%95>) |
|                                                              | [二、缺失数据的运算与分组]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC6%E7%AB%A0%20%E7%BC%BA%E5%A4%B1%E6%95%B0%E6%8D%AE.ipynb#%E4%BA%8C%E3%80%81%E7%BC%BA%E5%A4%B1%E6%95%B0%E6%8D%AE%E7%9A%84%E8%BF%90%E7%AE%97%E4%B8%8E%E5%88%86%E7%BB%84>) |                                                              |
|                                                              | [三、填充、剔除与插值]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC6%E7%AB%A0%20%E7%BC%BA%E5%A4%B1%E6%95%B0%E6%8D%AE.ipynb#%E4%B8%89%E3%80%81%E5%A1%AB%E5%85%85%E3%80%81%E5%89%94%E9%99%A4%E4%B8%8E%E6%8F%92%E5%80%BC>) |                                                              |
|                                                              | [四、问题与练习]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E7%AC%AC6%E7%AB%A0%20%E7%BC%BA%E5%A4%B1%E6%95%B0%E6%8D%AE.ipynb#%E5%9B%9B%E3%80%81%E9%97%AE%E9%A2%98%E4%B8%8E%E7%BB%83%E4%B9%A0>) |                                                              |
| [第7章 文本数据]()                                           |                                                              |                                                              |
| [第8章 分类数据]()                                           |                                                              |                                                              |
| [第9章 时序数据]()                                           |                                                              |                                                              |
| [第10章 可视化]()                                            |                                                              |                                                              |
| [第11章 有挑战性的例子]()                                    |                                                              |                                                              |
| [参考答案](  <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E5%8F%82%E8%80%83%E7%AD%94%E6%A1%88.ipynb#%E5%8F%82%E8%80%83%E7%AD%94%E6%A1%88>) | [第2章]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E5%8F%82%E8%80%83%E7%AD%94%E6%A1%88.ipynb#%E7%AC%AC2%E7%AB%A0%EF%BC%9A%E7%BB%83%E4%B9%A0%E4%B8%80>) | [练习一](  <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E5%8F%82%E8%80%83%E7%AD%94%E6%A1%88.ipynb#%E7%AC%AC2%E7%AB%A0%EF%BC%9A%E7%BB%83%E4%B9%A0%E4%B8%80>) |
|                                                              |                                                              | [练习二](  <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E5%8F%82%E8%80%83%E7%AD%94%E6%A1%88.ipynb#%E7%AC%AC2%E7%AB%A0%EF%BC%9A%E7%BB%83%E4%B9%A0%E4%BA%8C>) |
|                                                              | [第3章](  <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E5%8F%82%E8%80%83%E7%AD%94%E6%A1%88.ipynb#%E7%AC%AC3%E7%AB%A0%EF%BC%9A%E7%BB%83%E4%B9%A0%E4%B8%80>) | [练习一](  <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E5%8F%82%E8%80%83%E7%AD%94%E6%A1%88.ipynb#%E7%AC%AC3%E7%AB%A0%EF%BC%9A%E7%BB%83%E4%B9%A0%E4%B8%80>) |
|                                                              |                                                              | [练习二]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E5%8F%82%E8%80%83%E7%AD%94%E6%A1%88.ipynb#%E7%AC%AC3%E7%AB%A0%EF%BC%9A%E7%BB%83%E4%B9%A0%E4%BA%8C>) |
|                                                              | [第4章]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E5%8F%82%E8%80%83%E7%AD%94%E6%A1%88.ipynb#%E7%AC%AC4%E7%AB%A0%EF%BC%9A%E7%BB%83%E4%B9%A0%E4%B8%80>) | [练习一]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E5%8F%82%E8%80%83%E7%AD%94%E6%A1%88.ipynb#%E7%AC%AC4%E7%AB%A0%EF%BC%9A%E7%BB%83%E4%B9%A0%E4%B8%80>) |
|                                                              |                                                              | [练习二]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E5%8F%82%E8%80%83%E7%AD%94%E6%A1%88.ipynb#%E7%AC%AC4%E7%AB%A0%EF%BC%9A%E7%BB%83%E4%B9%A0%E4%BA%8C>) |
|                                                              | [第5章]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E5%8F%82%E8%80%83%E7%AD%94%E6%A1%88.ipynb#%E7%AC%AC5%E7%AB%A0%EF%BC%9A%E7%BB%83%E4%B9%A0%E4%B8%80>) | [练习一]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E5%8F%82%E8%80%83%E7%AD%94%E6%A1%88.ipynb#%E7%AC%AC5%E7%AB%A0%EF%BC%9A%E7%BB%83%E4%B9%A0%E4%B8%80>) |
|                                                              |                                                              | [练习二]( <https://nbviewer.jupyter.org/github/GYHHAHA/Joyful-Pandas/blob/master/%E5%8F%82%E8%80%83%E7%AD%94%E6%A1%88.ipynb#%E7%AC%AC5%E7%AB%A0%EF%BC%9A%E7%BB%83%E4%B9%A0%E4%BA%8C>) |

#### 四、版本要求

１、Pandas于2020年1月29日发布了1.0.0的版本，本项目全部使用新版本

```
Python: 3.6+
Numpy: 1.17.4
Pandas: 1.0.0
Matplotlib: 3.1.2
```

#### 五、反馈

１、欢迎任何有益的建议或想法，可邮件(1801214626@qq.com)交流！

２、不免有错误，欢迎提Issues！

#### 六、参考资料

1、[Python for Data Analysis](<http://93.174.95.29/_ads/A3AD6E6B2504B95EC39A6C57D465BA5D>) Wes McKinney著

2、[Pandas Cookbook](<http://93.174.95.29/_ads/23950B4446ABB5DD27168D6B0FB2C8DB>) Theodore Petrou著

3、[User Guide for Pandas v-1.0.0](<https://pandas.pydata.org/pandas-docs/version/1.0.0/user_guide/index.html>) Pandas开发团队编写