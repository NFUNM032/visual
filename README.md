# 我们对电影市场是否有真正的了解
#### 1. 项目背景 
电影市场现在总体来说呈现一个良好的发展趋势，电影的类型越来越多样，越来越贴近人民群众的生活，同时也在影响着人民群众的生活。但是还是有一些电影制作团队为了追求电影投入市场的速度，而采取快销式的电影，剧本相对粗糙，后期剪辑粗糙，更有甚者存在侵权的行为。

#### 2. 项目介绍
我想通过本项目对电影这个问题进行探讨以及对在豆瓣爬取的数据（主要是与电影评分相关的信息）进行可视化效果。 其中可能涉及的内容有：
- 豆瓣电影中的世界电影详细信息（包括标题、评分、导演、演员、时长等等）；
- 豆瓣电影中不同国家电影产量的统计；
- 豆瓣电影中top250的电影信息

#### 3. 项目的具体内容
- 世界电影可视化内容：
   - (1)不同国家电影产量统计；
   - (2)世界电影评分统计（世界电影评分统计、电影年度评分统计）；
   - (3)世界电影评分比例。
- top250电影可视化内容：
   - (1) 豆瓣top250电影分布地区；
   - (2)豆瓣top250电影中导演作品数量top10；
   - (3)豆瓣top250电影产源国家数量占比
   - (4)豆瓣top250中优秀演员参演作品数量。

#### 3. 项目数据的获取
对豆瓣电影信息的爬取

- 首先是在豆瓣电影上通过Chrome开发工具找到数据请求API进行数据的爬取，即能获取到所有电影的分类（tag）；
- 第二步是通过请求某个tag下的page_start和page_limit进行包括电影的标题、url、评分等电影数据的获取；
- 有了电影的url，可再次爬取该页面对应的html内容，最终一共获取了4800条电影记录，每条记录包含以下15个字段：电影ID、标题、链接、缩略图、评分、导演、编剧、演员、分类、上映国家、语言、上映时间、时长、别名和简介。

#### 4. 项目数据的清洗
将字段里多余的空白去掉、将上映时间仅保留年份、将时长处理为以分钟为单位的整数等。

#### 5. 呈现的数据故事
将在豆瓣中获取到的世界电影信息和top250电影信息进行分别的数据可视化，呈现两个不一样的数据故事
**世界电影信息的数据故事**：
结合所有数据 ，对不同国家电影产量统计进行可视化可以看出，大多数国家的电影产量都是少之甚少的，甚至为零。电影产量较多的主要有美国、中国、日本、英国、德国等国家；从大范围来看，该地图可视化能突出美国电影产量的多，但对于位于它后方的国家的电影产量不能有很明显的突出，从这个角度也可以看出，美国电影的产量多且数量上与其他国家有一大段距离。
不过电影数量的虽逐渐增多，却不知它们的质量如何。通过以上饼状图豆瓣电影评分比例以及折线图电影评分统计的分析可看出豆瓣上电影评分以6-8分最多，低于5分的电影以及高于8分的电影相对比例都比较少。只是没想到，最近纪念电影数量虽多，平均评分却有走低的趋势。不知道是因为观众的口味变了还是电影本身变了呢？

**top250电影信息的数据故事**：
在获取电影来源国家时，有些电影是两个或两个国家以上合拍的，所以在统计时，每当涉及一个国家时都会对这个国家出的作品加一。从这张可视化地图以及饼状图可看出，top250电影数量最多的产源地是美国，共有138部，一方面是这个国家处于一个多元形态，能够碰撞不一样的题材，另一方面是美国的电影制作技术较为成熟，能够产出刺激视觉的片子；排在其后的是日本、英国等。其中，值得注意得是中国香港的电影质量也是相对不错的，中国大陆的电影虽然从前面的产量统计来看是位列前茅的，但高质量电影的拥有量还是过少的，因此大陆在电影方面的发展仍需不断进行借鉴与提高。
另外，从爬取的数据中对这些经典电影的导演做了一个简单的统计，对于导演作品数量进行了一个排名，取了前十名；其中，王家卫导演和李安导演也位列其中，且分别以5部电影和4部电影居于第三名和第六名，这是观众对他们作品的一个肯定。其次，在对电影制作与电影技巧有更高追求的电影制作人来说，学习与借鉴这些优秀导演的作品是极具价值的。
如今，许多人都在批评小鲜肉的演技，认为如今对演员的侧重点有所偏离，只注重颜值、流量，而缺乏演员最基本以及必备的演技。因此，我们根据演员的参演作品数量做了一个“漏斗图”，在这250部经典电影中，参演作品数量最多就是哥哥张国荣，一共8部之多，接下来就是张曼玉，参演过7部，而星爷跟刘嘉玲一共参演过4部，他们都是当今时代演员的学习标杆。



