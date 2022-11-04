---
title: CLP-SHOPPING仿写踩坑记录
date: 2022-10-14 11:23
description: 首页+登录
tags: 实战系列
---

### 商城项目实战①

**项目名称：**NiceDay

**技术栈：**React + ReactHook + ReactRouter + Redux + Axios +other

**计划完成功能：**

- 首页展示

**计划完成进度：**1/7 days

#### 学习困难:

1. **环境构建：**

- **项目环境：**create-react-app 脚手架构建项目
  - npx create-react-app NiceDay
- **支持less语法：**
  - 执行命令：npm run eject（注意使用此命令src不能有任何修改）
  - 安装依赖：cnpm install --save-dev less less-loader
  - 修改webpack.config.js文件：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDeC26oWvC1pgzQK5_697_96.png_720x10000.jpg)

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDeREaSrIop7Mlc0Cqw_683_149.png_720x10000.jpg)

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDf0i36wsYCDNBN7NAxI_786_1246.png_720x10000.jpg)

- **集成网络请求Axios**
  - 安装依赖：cnpm i --save axios
  - 配置相关文件：
    - axios文件request.js：二次封装
    - 接口文件api.js：请求方法
- **设置rem布局**

在index.html文件中添加动态rem计算方法

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDfYH4mhjj6fNAsDNBR8_1311_704.png_720x10000.jpg)

- **配置初始样式**

引入iconfont文件：这里我使用的是阿里矢量图标库，然后在页面导入

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDeREaSuZVQbM6Mzy_242_232.png_720x10000.jpg) 

2. **路由配置**

- **创建页面：**Home/Life/Shop/User
- **创建路由：**
  - 安装依赖：cnpm i --save react-router-dom
  - 配置路由：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDf0i365eZDnNAb7NA_g_1016_446.png_720x10000.jpg)

#### 学习心得与感悟:

由于教程并非最新教程的原因，在观看实战教程时搭建项目也遇到些许问题，很多出现在版本问题。比如最新版react已经不支持querystring、Switch、component等，已经改为最新版本的URLSearchParams/Routes/element...

**① less配置：**开始配置less后却一直不生效，查找了一番归结于版本问题，于是降版本安装less-loader5.0.0版本，成功生效。

**②** **路由配置：**

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDeREaSwNWRsqzQQX_1047_42.png_720x10000.jpg)

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDf0i362Qen1SzQOS_914_82.png_720x10000.jpg)

配置时出现这些报错原因均为'Switch' 和'Redirect' 是 react-router 5版本的接口，而最新版本是"react-router-dom": "^6.2.1"，并且已经将Switch改为Routes。

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDf0i364VRbrMps0DAQ_769_166.png_720x10000.jpg)

由于component已经被替换成element，在使用时不能：

<Route exact path="/" element={ Home }></Route>

而是：

<Route exact path="/" element={ <Home /> }></Route>

终于不再报错，成功运行。

**③导航样式：**

NavLink的默认颜色为蓝色而且带有下划线，消除下划线需要text-decoration：none，更改颜色需要给NavLink定义加一个className，然后再写样式color：gray；

**今天的任务并不算很多，但是既要跟上配置思路，又要自己重新敲一遍代码，还有很多很多的版本问题，纠错基本上就花了至少1-2h，很多时候是这个问题解决又引发下一个问题，不过这也很好地锻炼了我的解决问题能力，之前自己写项目的时候不是特别规范，很多细节都是随便处理，解决了就行了，完全不管他代码的整洁程度以及有没有将代码分类。我相信在跟练完这个实战项目后我也可以独立开发出一个质量较高的项目！**



### 商城项目实战②

**项目名称：**NiceDay

**技术栈：**React + ReactHook + ReactRouter + Redux + Axios +other

**计划完成功能：**

- 首页展示
- 充值中心
- 选择套餐
- 购物中心
- 商品详情
- 个人中心
- 个人详情
- 登录注册

**计划已进行：**2 days

由于个人能力+精力+条件有限，仅能实现部分界面。

**今日参考界面：**

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDgCwXmOn0U7NBDTNA2o_874_1076.png_720x10000.jpg)





#### 学习困难:

1. **修改底部导航**

- **代码规范问题**

今天师傅给我发了一份公司的ES6规范，本来是下载FishX插件当做Eslint用，但是不知道为啥在我电脑上没作用，所以还是用的Prettier插件，还可以一键格式刷，方便又快捷。

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDefR5-JFHgV0zQQu_1070_116.png_720x10000.jpg)

- **图标问题**

- 之前用的<i/>写的图标，但是师傅给的这个设计稿只能将图标图片下载到本地，奈何 i 标签没有src属性，于是改用<img/>：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDe7s5SuFHuVIzQOp_937_72.png_720x10000.jpg)

- 写了之后图片刷不出来，以为是地址问题/名称问题纠结了十几分钟问师傅，原来是react导入图片地址要先import图片路径给变量，然后导入变量才可以：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDf0i376nJPYzzQQ5_1081_51.png_720x10000.jpg)

图标问题就此解决

- 框架问题

在昨天写的界面中我的框架是这样的，每一个都单独写出来，代码十分冗余。

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDetfZoa-A3bNArfNA_Y_1014_695.png_720x10000.jpg)

师傅说但是为了代码美观简洁，开发中会将li的数据写成数组，进行遍历，要求尽量将数据格式mock成接口返回的格式，方便后续接口调试，减少工作量。在此之前我只写过vue的多级菜单有采用到v-for循环遍历填充，今天学习了**在react中采用map遍历数组**的方式进行高效开发：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDfmVYRnn6ZDNAwvNBjc_1591_779.png_720x10000.jpg)

然而我还是太天真了，想要将图标名和图标地址一起传入li中，于是创造出了这样一个四不像的"数组"，报错后又去求救师傅，师傅说我的对象数组写的不像mock格式，让我将图表名和地址都放在对象里，给他们分别加上键名。于是我顺利完成：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDfYH4nVdph_NA03NBVo_1370_845.png_720x10000.jpg)

- **定位问题**

通过上面操作，我们已经可以得到如下导航栏：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDfJ6Y9C8YCLMvs0C7g_750_190.png_720x10000.jpg)



显然跟设计稿还有些差别，这个问题我第一想法是：绝对定位。但我很快认识到这样子是行不通的，我既然已经遍历数组生成了li，那我应该只需要把他们做底部对齐就行，所以很快就想到了**flex+align-items**的用法，成功解决问题~



![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDfYH4nV1mBrMt80DOw_827_183.png_720x10000.jpg)

2. **修改顶部导航**

有了底部导航栏的实践，顶部导航栏对我来说容易多啦，需要注意的是对齐问题以及间距问题

- **框架**

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDetfZocrFJDNAgrNBQg_1288_522.png_720x10000.jpg)

- **样式**

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDfmVYRpeirLNApXNBHw_1148_661.png_720x10000.jpg)

- **界面**

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDfYH4nWIfwvMjs0Ddg_886_142.png_720x10000.jpg)

3. **今日完成界面**

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDfJ6Y9DKtgLNBQLNAz0_829_1282.png_720x10000.jpg)

4. **今日遗留问题：**

可以看到底部导航栏的字体颜色，按道理说应该在进入界面时默认情况下home字体与图标为标蓝状态，而后哪个按键被点击哪个就会标蓝，但是我采用的是NavLink编写的路由跳转，所以即使给它样式覆盖也只能做到开始时统一为黑色，当点击时才会标蓝。师傅说我可以用a标签写，自定义点击事件跳转与状态改变，这样子可以解决问题。师傅的思路我理解了，但还没来得及实现，我的想法是目前先把静态页面做完，等到页面大致做完后再加入js事件，完善细节问题。

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDfYH4nV1mBrMt80DOw_827_183.png_720x10000-166538606400154.jpg)

#### 学习心得与感悟:

从今天早上开始看到公司开发规范的时候就知道我要学习的东西还有很多，我不能为了实现界面和功能而不管代码的清晰度，简洁度以及美观度，而是要在完成的基础上一定要做到代码规范问题。在我之前的项目开发中，代码有点乱七八糟（应该不止一点），对于团队协作以及后期维护来说简直是灾难，经过这次仿写项目，我要做到代码规范+实现react开发项目，了解到更多react的相关开发知识。明天的开发应该会比今天的进展要顺利一些，今天在编写代码时，有很多问题都思考欠缺，比如导航栏定位问题，想当然的先用绝对定位去做了，结果师傅不仅纠正了我的代码简洁规范，还纠正了我开发时的错误思想，是我的代码救命之星。最后感谢小马哥给我安排上了大显示屏，我的神！

#### 

### **商城项目实战③**

**项目名称：**NiceDay

**技术栈：**React + ReactHook + ReactRouter + Redux + Axios +other

**计划完成功能：**

- 首页展示
- 充值中心
- 选择套餐
- 购物中心
- 商品详情
- 个人中心
- 个人详情
- 登录注册

**计划已进行：**3 days

**今日参考设计稿：(已划分盒模型)**

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDefR5_Ao_9rNAjDNA2w_876_560.png_720x10000.jpg)



#### 学习困难:

1. **创建顶部主要功能栏**

- **宽高问题：**

写这个功能栏的时候，采用的ul+li结构，跟昨天一样用的数组遍历生成li，但是我犯了一个小错误，我将ul的宽度设置成了100%，导致如下问题：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDgCwXnGPKmbNBp7NA-Q_996_1694.png_720x10000.jpg)

可以看到横向和纵向都出现了滚动条，无法看到完整界面，我询问师傅后，师傅提示我滚动条出现的原因是因为里面的元素宽度或者高度大于外面的元素，然后让我去思考是哪个元素的高或者宽有问题。我今天有问过师傅，是不是在开发H5项目的时候所有的px都要写成rem，师傅给予肯定回答，所以当我在查找错误元素时，发现我有设置过ul：100%，顿时恍然大悟，将其改为和设计稿对应尺寸的rem布局瞬间恢复正常。**外层盒子尽量不要设置宽高，因为你无法肯定它的大小，尽量使它的宽高是被元素撑起来的。**

2. **创建PostPaid卡片栏**

- **框架问题**

在看见卡片的设计稿时，我有一点点不知道从何下手，它的盒子该怎么嵌套，我开始的想法：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDetfZpUX9zXNAZLNA4g_904_402.png_720x10000.jpg)

但是我很快否定了，这样会有一些地方不好对齐，实现难度增加，在询问了师傅的意见后，我的框架改成了：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDfmVYSgIRuTNAmPNBMM_1219_611.png_720x10000.jpg)



- **div大小问题**

在开发points部分的时候，我遇到了一个非常棘手的问题：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDfJ6Y96jJy_NAsrNAn0_637_714.png_720x10000.jpg) 

这个问题困扰了我将近一个小时，**为什么div的高度会远远大于内部元素高度(我并没有设置宽高)**，很难解决，我去搜索不知道该怎么搜，后面一起和师傅好好研究了十来分钟，发现是fontsize捣的鬼，我的fontsize默认为50px，方便计算rem，然而这50px的基准值可干扰到了div的高度：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDfJ6Y96Na3jNAh7NAt4_734_542.png_720x10000.jpg)



![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDetfZpUjBCQnzQIE_516_39.png_720x10000.jpg) ![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDgCwXnHCKQJszPI_242_108.png_720x10000.jpg) 

通过上面三个证据可以看到 **div高度 = font-size + 元素高度**，这下真相大白，有了上网搜索的关键词了，一搜还真让我找到了：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDf0i380JmtHNAyPNBtU_1749_803.png_720x10000-16657178594531.jpg)

我尝试了第一种：white-space：pre-line，可惜没有作用，于是我使用第二种：**在全局公共样式里加上font-size：0px；**问题解决了，就在我和师傅说的时候，他说这种做法可以暂时解决问题，但**并不是一劳永逸的**方法，为什么呢，如下：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDfYH4oNmt5PNATjNBVA_1360_312.png_720x10000.jpg)

所以说这种方法只能做到解决部分div宽高问题，如果全局适用会对后面的代码产生影响，我想要彻底解决问题应该需要将font-size基准值调整到合适大小。

3. **今日遗留问题**

**我的图：**

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDefR5_CYSc5ZzQK-_702_89.png_720x10000.jpg)



**设计稿：**

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDgCwXnHrR6RIzQKQ_656_72.png_720x10000.jpg)



我开发的界面两条小竖线没有对齐，我还没有想到合适的方法加，本来说在存储数字的div右边边框加上border就能实现，但是这个布局用的flex而且单位长度不一样，边框的效果看起来就不是对齐的，我在思考是将div宽度再设置的合理一些，还是加margin什么的，又是今日留下来的小问题！

4. **今日完成界面**

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDetfZpWbh-PNBQbNA0Y_838_1286.png_720x10000.jpg)

#### 学习心得与感悟:

1. 开发规范：

- 在开发web时大小使用px，但开发移动端项目时大小使用rem；
- 尽量不要给外层盒子定义宽高，以免开发到后期出现问题不好返工；
- 开发中尽量不使用id设计样式，采用class会方便许多，class的定义最好按照功能来，这样哪个元素需要只需要加上class就行，class可以对应多个元素。

2. 设计细节

我觉得很难的一点就是前端开发中所有元素大小间距定义都要根据设计稿来，非常非常揪细节，也许偷懒只想复现的时候看起来差不多就行了，但是绝对不能这样子，不能为了偷一时懒不顾项目的安危。

今天的开发进度依旧不是很快，常常会在一些细节地方卡住，导致完成效率不高，终归还是练习的不够多，目前的css不够熟练(等到界面开发完可能就是js不熟练了哈哈)，只能勤能补拙，每天做好自己的任务，不会的尽量自己解决，实在解决不了的就问师傅，可以重点培养自己解决问题的能力，加深对知识点的印象。好好写日志就相当于给自己每天的工作记录重点内容，建立好的错题本，是以后开发中必不可少的步骤！(明天要开发的应该要借用到antd-mobile里的swiper，今天浅看了一下，没有太看懂，明天早上再细细研究)

#### 

### **商城项目实战④**

**项目名称：**NiceDay

**技术栈：**React + ReactHook + ReactRouter + Redux + Axios +other

**计划完成功能：**

- 首页展示
- 充值中心
- 选择套餐
- 购物中心
- 商品详情
- 个人中心
- 个人详情
- 登录注册

**计划已进行：**3 days

**今日参考设计稿：(已划分盒模型)**

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDgCwXnthbyjNA4zNBAA_1024_908.png_720x10000.jpg)

#### 学习困难:

1. **创建功能滑动界面**

- **Tabs+Swiper组合**

一开始打算使用这俩组合开发这个界面的时候，没有很熟练，我想要做到既遍历循环生成li，又使li有两排，我的最初想法是一个div内嵌套两个ul，然后每个ul各自遍历长度为4的数组生成2*4的布局，如下：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDf0i39bMSLDNBFPNA3k_889_1107.png_720x10000.jpg)

结果这种方式生成了2*8的结构，于是我求救了师傅...

师傅说我可以创建长度为8的数组，只使用一个ul循环就行，既解决问题又减少代码冗余。事实证明确实可以哈：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDeC26rCtgzHNAsLNA9M_979_706.png_720x10000.jpg)

最后的整体swiper+tabs长这样：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDeC26rC7fGvNAlPNBOU_1253_595.png_720x10000.jpg)

- **tabs标题栏问题**
  - **下划线问题**

由于用的antd-mobile里的组件，所以样式很多都是自带的，并不好修改。比如我没法直接修改它的标题栏选中时的下划线，至少不能用图片直接代替。

**自带的：**

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDfmVYTJRDz7MlM0C6A_744_148.png_720x10000.jpg)

**设计稿：**

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDe7s5UQM3F9-zQMG_774_126.png_720x10000.jpg)

不过师傅给了我一个非常棒的思路：可以**试试用伪元素替换一个图标上去/画一个半圆**。因为有图标素材，所以直接使用的伪元素添加图片：![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDf0i39c_rbHNAozNBMw_1228_652.png_720x10000.jpg)

前提是要**先隐藏之前的下划线，然后使用伪元素::after放在title下面，再水平居中**就可以。

- **大小问题**

我之前的底部导航栏+顶部功能栏+卡片界面宽度全部设置的rem大小，突然出现的tabs宽度影响到了整体的布局，虽然他也只有375px的宽度，但是整个盒子都被他撑开了，造成左右出现间隙：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDe7s5UQpGZ3NASfNA74_958_295.png_720x10000.jpg)

我思考了一会**把之前的所有ul、div只要是设置了rem宽度的全部改成100%**，果然界面恢复正常，不再左右滑动。

- **文字换行问题**![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDgCwXnwoDOLMms0C5w_743_154.png_720x10000.jpg)

在设计图中，可以看到功能名称都是一个单词占据一行，但是我用的span做不到换行：![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDe7s5UQ0kMXM4szB_193_226.png_720x10000.jpg) 

我想了很久问了师傅，师傅给了我一个解决方案：**将ul的flex-wrap设置为wrap，把li的宽度设为min-content**：![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDfmVYTKUYF7NBTjNC7I_2994_1336.png_720x10000.jpg)

但是这样依旧没有解决问题，我的排版甚至变得混乱，于是我选择使用p标签框住文字，然后所有改动在p标签内进行，成功实现：(当然最主要的还是**flex-wrap: wrap**)

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDetfZp-HaBfNAxTNBFo_1114_788.png_720x10000.jpg)

2. **创建广告图**

这个基本上就只需要加一个图片，成果如下：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDf0i39dyXFnNAeLNA9c_983_482.png_720x10000.jpg)

3. **返工之前代码**

- **图片尺寸**

每个图片都要设置宽/高，给一个就行，因为图片宽高比是固定的。之所以要设置尺寸是因为如果屏幕大小不一样，图片可能在大屏手机和小屏手机上看着效果不一样，统一rem尺寸看起来差别就不会很大。

- **框架设计**

这个是师傅看见我的顶部导航栏给我的建议，开发之前研究界面的时候可以把整体框架先设计好，比如我的导航栏是贴着顶部的，加了个margin，但其实在开发中一般会选择在最外层边框加个padding就解决了，结构看着也清晰一些，不会出现margin塌陷问题。

4. **今日遗留问题**

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDetfZp_Gd3XMrs0DcA_880_174.png_720x10000.jpg)

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDgCwXnx0VMfMkM0D2g_986_144.png_720x10000.jpg)

可以看到我的两个标题之间距离跟设计图上并不一致，我有尝试过修改tabs的样式，比如把padding去掉、把space-around改成space-between或者是修改他们外层div的宽度，但这些都没有效果，起码尝试修改了有一个小时吧，但是还是做不到，毕竟这个东西是封装好的，我暂时还没有解决办法，也许以后会有。

5. **今日成果展示**

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDf0i39mO_jDNBO3NA8E_961_1261.png_720x10000.jpg)





#### 学习心得与感悟:

今天为止就是把首页的页面写完了，还有一些小的细节没写，比如说点击更多会出现下拉菜单，点击菜单栏右侧会出现滑动菜单之类的交互还没有开始写。今天学到了swiper+tabs布局完成标签页的制作，以及一些代码规范，比如上面说的图片尺寸和框架搭建问题，不能想当然的去写，要知道这些规范设计的原因。下一步的计划是想完善未完成的细节问题，在这过程中尽力解决遗留问题，其次就是尝试调用接口去展示数据，而不是像现在一样是一个静态界面。在调用接口时肯定会出现其它问题，就像师傅说的不定长文本过长溢出了怎么办（css解决单行文本溢出），不同长度的文字布局展示间距怎么办，这都是接下来我需要面临的问题。

------

### **商城项目实战⑤**

**项目名称：**NiceDay

**技术栈：**React + ReactHook + ReactRouter + Redux + Axios +other

**计划完成功能：**

- 首页展示
- 充值中心
- 选择套餐
- 购物中心
- 商品详情
- 个人中心
- 个人详情
- 登录注册

**计划已进行：**4 days

#### 学习困难:

1. **新增下拉菜单**

- **Dropdown组件**

来自ant design的组件，不过使用起来感觉不是很好，比如刚开始使用的时候效果如下：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDfYH4q6GkcvNATzNA3Q_884_316.png_720x10000.jpg)

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDfJ6ZAnNAYrNBEDNA9Y_982_1088.png_720x10000-16657179146073.jpg)

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDf0i3_gHFivMpc0DfQ_893_165.png_720x10000.jpg)



我问了师傅，师傅说我的antd样式没有生效，比如点击li后下面没有关于antd的class样式，之后知道应该是由于我的是react项目直接拿脚手架建的，不是用的umi，导致webpack配置没有弄好，需要自己引入antd.css，所以加了一条：**import 'antd/dist/antd.css';**

但是，就是因为加这么一句，导致我其他地方本来写好的地方又开始布局混乱，像这样：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDefR6Bt5ghvNAljNAx0_797_600.png_720x10000.jpg)



![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDgCwXpz38FbNAhLNAsA_704_530.png_720x10000.jpg)



我的所有文字标签都被自动增加了一个和我fontsize一样大的margin，这个地方纠结了至少一个小时，最后师傅和我说是因为antd样式覆盖了全局的样式，我觉得antd这个组件好难用啊，要达到设计图的效果需要费好大功夫，所以我把dropdown组件去掉了，原生写了一个下拉菜单组件，目前是这个样子：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDgCwXpz57N3NARrNAyg_808_282.png_720x10000.jpg)

等到我把antd样式覆盖问题解决好了再考虑用antd吧，其实除了样式覆盖问题，由于我这是img，而官方举例采用的都是button，导致这样点击后下拉菜单的样式和位置对我来说都挺难调整的。



2. **新增mini功能滑动小程序：**

- **min-content**

之前写上一个hot功能滑动小程序的时候，由于单词很短也需要换行，所以在p标签内加了一个width：min-content，但是写mini功能的时候不需要，不然就变成了这样：

我写的：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDeC26tIG2-nNAp3NBCI_1058_669.png_720x10000.jpg)

设计稿：

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDefR6BuRsXrNAh7NAxI_786_542.png_720x10000.jpg)

在意识到应该是min-content引发的问题之后，我单独给hot功能界面设置了一个class，其他的为默认，这样就解决问题了。

3. **今日遗留问题：**

今天引发的问题就是antd的样式覆盖了全局样式的问题，以及我的项目每次启动进去的时候都会有横向滚动条，但是刷新几次后又恢复，不知道什么原因，打算抽空仔细看**《CSS世界》**纠错。这本书很好，强烈推荐给大家，包括它的新版**《CSS新世界》**。

1. **今日完成界面：**

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDeREaXbSx6XNBOnNA24_878_1257.png_720x10000.jpg)

#### 学习心得与感悟:

今天也算是特别感受到了什么叫做一台电脑一杯水，一个bug改一天的感觉。今日进度勉强完成，还有些没有完成，不过首页的，剩下的很多功能都是需要接口的，比如根据用户登录状态判断postcard组件的展示状态，包括点击菜单弹出侧边菜单，都是还没有实现的。写前端没有想象中容易，要考虑的地方很多，遇到的问题也有很多，不适配、版本不一致、属性冲突等等，而且还要考虑代码的美观、简洁。明天研究一下webpack的配置，看看能不能解决antd样式问题，接口方面尝试mock模拟数据看看有没有问题。一个项目真的不能是一个人的心血，起码也得是一群人的心血，一个人写可能几个月也做不好一个像样的项目，太多的逻辑需要考虑。明天继续加油。

### **商城项目实战⑥**

**项目名称：**NiceDay

**技术栈：**React + ReactHook + ReactRouter + Redux + Axios +other

**计划完成功能：**

- 首页展示
- 登录注册

**计划已进行：**5 days

**今日完成界面：**

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDefR6E4yKknNAvbNAfI_498_758.png_720x10000.jpg) 

由于只是想写一个测试用的登录，所以就没有写成各个组件了，全部写在login.js一个文件里。

#### 学习困难:

- **输入框输入无效问题**

因为我引入antd会导致覆盖全局样式，所以用的是原生表单，修改样式写的，但是遇到了一些小问题：首先是报警告说我没有写onChange属性，看到后我就加了，但是name、value都是默认的；之后就是输入文字但不显示，我在网上没有搜索到答案，问了师傅后，师傅说因为我写了**value=""**，这个表示实时更改，只要input输入框内容发生变化就会自动替换为value，也就是空的，所以我输入什么内容都失败。

![img](CLP项目仿写踩坑记录/lALPDf0i4Cs-_xfNASrNA8Y_966_298.png_720x10000.jpg)

- **底部导航栏问题**

我之前写的bottomBar组件使用的fixed定位，所以为了可以在每个页面都显示底部栏，就把他放在了router.js里面，但是这样子登录注册界面也会有导航栏，这个问了师傅，说是要写两套不同布局，但我还没搞明白，暂时遗留问题，尽量这两天解决。

- **获取token问题**

1. **新增username&&userpwd数据，初始值为空，绑定store**

![img](CLP项目仿写踩坑记录/lALPDetfZvPKFFjNBB7NAtY_726_1054.png_720x10000.jpg)

2. **在actions.js的setLogin方法中添加异步数据请求，设置token**

![img](CLP项目仿写踩坑记录/lALPDfJ6ZD074iXNAvrNAt8_735_762.png_720x10000.jpg)

![img](CLP-SHOPPING 项目仿写踩坑记录/lALPDfmVYYbjHl_NAXXNAvc_759_373.png_720x10000.jpg)

3. **解析token**

![img](CLP项目仿写踩坑记录/lALPDeREaapDYSDNA6LNAto_730_930.png_720x10000.jpg)

![img](CLP项目仿写踩坑记录/lALPDe7s5ZiTV3rNAtjNAtg_728_728.png_720x10000.jpg)

4. **页面判断用户输入**

![img](CLP项目仿写踩坑记录/lALPDfJ6ZD1czTrNAQ7NA2Y_870_270.png_720x10000.jpg)

- **页面刷新数据消失问题**

![img](CLP项目仿写踩坑记录/lALPDeC26wV7S43NA0DNAzo_826_832.png_720x10000.jpg)

#### 学习心得与感悟:

今天写页面写了四五个小时，解决token问题不是很顺利，看到的教程有自己写后台接口的哈哈，但是我这只能自己模拟，所以麻烦了一点，主要解决就是路由传参，不过我觉得可能我的路由实现方式不是太好，这两天看看能不能改成适合项目使用的方式，还剩下的底部导航栏问题，可能就是由于不适合写在路由里。我看了clp项目的源码，暂时没找到入口文件在哪，和我的好像有点差别，所以也无法借鉴这个项目来更正。这两天目标是解决导航栏问题，深入学习下现在的多种路由实现及跳转方式。

