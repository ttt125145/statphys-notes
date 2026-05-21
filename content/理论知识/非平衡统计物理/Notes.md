
# 从 Zwanzig 《非平衡统计力学》整理的一条研究思路


## Part 1


### 相空间 , 广义相空间



**相空间**：

用$q_1,q_2,\cdots,q_f$和$p_1,p_2,\cdots,p_f$作为直角坐标系构成2f维空间，称为相空间。

系统的微观状态是相空间上的一点，后面称为代表点。

孤立系统不随时间变化，$H(q_1,q_2,\cdots,q_f;p_1,p_2,\cdots,p_f)=E$，确定一个能量"超曲面"，代表点一定在"曲面"上。 

相空间中，一对 $q_i,p_i$  作为一个**自由度**，由**哈密顿正则方程**约束。 


**广义相空间**

不限于用 基本单元 的$p,q$ 去组成维度，也不限于 哈密顿正则方程作为维度的约束。

一个经典的广义相空间。其维度由 基本单元 的某个或多个属性 X 组成 ，所有维度唯一限制是在无穷远处为0。

广义相空间可推广到很多非物理空间。待会会看到。

### 哈密顿正则方程

$$
\begin{gather*}
\frac{\partial H}{\partial p}=\dot{q}\\
-\frac{\partial H}{\partial q}=\dot{p}
\end{gather*}
$$

证明：
$$
\begin{gather*}
H= \frac{p^2}{2m}+V \\[1em]
上式两边分别对p,q求偏导:\\[2em]
\frac{\partial H}{\partial p}=\frac{P}{m}=v=\dot{q}\\
-\frac{\partial H}{\partial q}=- \frac{dV}{dq}=F=ma=m \frac{\partial\dot{q}}{\partial t}= \frac{\partial m\dot{q}}{\partial t}=\frac{\partial p}{\partial t}=\dot{p}
\end{gather*}
$$

### 高斯散度定理及其微分形式

矢量场$\mathbf{F}$的闭合曲面积分是其散度的体积分：

$$
\iint_{\partial V} \mathbf{F} \cdot d\mathbf{S} = \iiint_V (\nabla \cdot \mathbf{F}) \, dV
$$


在物理应用中，某种“物质”的通量可表示为 $\rho \mathbf{v}$, 也是一个矢量场，可作为上式的$\mathbf{F}$。
$$
\iint_{\partial V} \rho\mathbf{v} \cdot d\mathbf{S} = \iiint_V \nabla \cdot (\rho\mathbf{v}) \ dV
$$
此式可看作“物质” 在单位时间流出闭合曲面的总“质量”。

另一方面，可以用质量的时间导数$\frac{d}{dt}\iiint \rho dV$来表示单位时间质量变化。

$$
\frac{d}{dt} \iiint_V \rho \, dV = - \iiint_V \nabla \cdot (\rho\mathbf{v}) \ dV

$$
取消两边的积分并移项：
$$
\frac{\partial \rho}{\partial t} + \nabla \cdot (\rho \mathbf{v}) = 0
$$
这是高斯定理结合质量连续性得到的方程，一般叫做连续性方程。



### 刘维尔算子 ， 类刘维尔算子


**刘维尔方程是相空间中的连续性方程，此外有哈密顿正则方程的约束**


在相空间中，对应为：
$$
\frac{\partial f}{\partial t} = -\frac{\partial}{\partial \mathbf{q}} \cdot \left( \frac{d\mathbf{q}}{dt} f \right) - \frac{\partial}{\partial \mathbf{p}} \cdot \left( \frac{d\mathbf{p}}{dt} f \right), \tag{2.7}
$$
​	用哈密顿正则方程
$$
\frac{\partial H}{\partial \mathbf{p}}=\dot{\mathbf{q}} \quad,\quad
-\frac{\partial H}{\partial \mathbf{q}}=\dot{\mathbf{p}}
$$
​	替换上式中的$\frac{dq}{dt}, \frac{dp}{dt}$,并将右边对$f$的操作定义为刘维尔算子$\mathcal{L}$:
$$
\mathcal{L}= \frac{\partial H}{\partial \mathbf{p}} \cdot  \frac{\partial }{\partial\mathbf{q}}   - \frac{\partial H}{\partial\mathbf{q}} \cdot \frac{\partial }{\partial\mathbf{p}} 
$$
​	上面的定理变为：
$$
\frac{\partial f}{\partial t}=-\mathcal{L}f
$$
​	这就是**刘维尔方程**。

​	其算子形式的解是:
$$
f(\mathbf{p,q}, t) = e^{-\mathcal{L}t} f(\mathbf{p,q}, 0). \tag{2.11}
$$


**类刘维尔方程是广义相空间中的连续性方程（高斯散度定理的微分形式）**

只需满足连续性方程：
$$
\frac{\partial f}{\partial t}  = - \nabla \cdot (f \mathbf{v})
$$
令：
$$
\mathcal{L} = - \nabla \cdot (f \mathbf{v})
$$

并类比于刘维尔定理：
$$
\frac{\partial f}{\partial t}=-\mathcal{L}f
$$


### 动力学变量A满足的演化方程
（相空间形式，广义相空间形式）

用刘维尔算子也可以简化表示任意动力学量的时间变化率。

在相空间中，
$$
\begin{aligned}
任意动力学变量,&是相空间坐标和时间的函数:A(\mathbf{q,\mathbf{p}},t)\\
\frac{dA}{dt} &= \frac{\partial A}{\partial \mathbf{q}} \frac{d\mathbf{q}}{dt}+ \frac{\partial A}{\partial \mathbf{p}} \frac{d\mathbf{p}}{dt}\\
&= \frac{\partial A}{\partial \mathbf{q}} \frac{\partial H}{\partial p}- \frac{\partial A}{\partial \mathbf{p}} \frac{\partial H}{\partial q}\\
&=\mathcal{L}A 
\end{aligned}
$$
​	算子解是$A(t)=e^{t\mathcal{L}}A(0)$  。

在广义相空间中，
$$
\begin{aligned}
任意动力学变量,&是相空间坐标和时间的函数:A(\mathbf{X},t)\\
\frac{dA}{dt} &= \frac{\partial A}{\partial \mathbf{X}} \frac{d\mathbf{X}}{dt}\\
&= \frac{\partial A}{\partial \mathbf{X}} \mathbf{v}=\nabla \cdot (A \mathbf{v})\\
&=\mathbf{L}A 
\end{aligned}
$$


## Part 2

### 从刘维尔方程  推导  福特普朗克方程

刘维尔方程 描述系统概率分布的演化,福特普朗克方程 是 刘维尔方程+ou过程 的数学重排。
（默认在广义相空间中）

系统在某个广义相空间中的坐标用$\mathbf{a}$表示。

其连续性方程：
$$
\frac{\partial f}{\partial t} + \frac{\partial}{\partial \mathbf{a}}\left(  \frac{\partial \mathbf{a}}{\partial t} \right)f = 0 \tag{2.34}
$$
其刘维尔方程为：
$$
\frac{\partial f}{\partial t}=-\mathcal{L}f
$$
其中，
$$
\mathcal{L}f= \frac{\partial}{\partial \mathbf{a}}\left( \frac{\partial \mathbf{a}}{\partial t} f \right)
$$
一个重要假设，系统动力学演化是个OU过程：
$$\frac{\partial \mathbf{a}}{\partial t}=\mathbf{v}(\mathbf{a})+\mathbf{F}(t) \tag{2.31}$$
$\mathbf{v}(\mathbf{a})$是$\mathbf{a}$函数，$\mathbf{F}(t)$是随机涨落,且满足
$$
\begin{aligned}
&⟨\mathbf{F}(t)⟩=0,
\\&⟨\mathbf{F}(t)\mathbf{F}(t^{'})⟩=\mathbf{B}δ(t−t^{'}).
\end{aligned}
$$

结合2.31和2.34得：
$$
\frac{\partial f}{\partial t} =- \frac{\partial}{\partial \mathbf{a}}(\mathbf{v}(\mathbf{a})f+F(t)f)
$$
重新整理一个算子$\mathbf{L}$，相比$\mathcal{L}$,只包含$\frac{\partial \mathbf{a}}{\partial t}$中的连续项，
$$
\mathbf{L}f= \frac{\partial}{\partial \mathbf{a}}(\mathbf{v}(\mathbf{a})f)
$$
则$f$的时间导数可表示为
$$
\frac{\partial f}{\partial t} = -\mathbf{L}f - \frac{\partial}{\partial \mathbf{a}}(\mathbf{F}(t)f) \tag{2.39}
$$
求解方式是凑积分因子$e^{-tL}$，并对时间积分([[V1#福特普朗克方程算子解(2.40)]])
$$
f(\mathbf{a},t)=e^{−tL}f(\mathbf{a},0)−∫_0^tdse^{−(t−s)L} \frac{\partial}{\partial \mathbf{a}}\mathbf{F}(s)f(\mathbf{a},s) \tag{2.40}
$$
用公式(2.40)表示的$f(\mathbf{a},t)$替换公式(2.39)中的噪声项$-\frac{\partial}{\partial \mathbf{a}} \cdot [\mathbf{F}(t) f]$ 中的 $f$:


$$
\begin{aligned}
-\frac{\partial}{\partial \mathbf{a}} \cdot [\mathbf{F}(t) f(\mathbf{a}, t)] &= -\frac{\partial}{\partial \mathbf{a}} \cdot \left[ \mathbf{F}(t) \left( e^{-tL} f(\mathbf{a}, 0) - \int_0^t ds \, e^{-(t-s)L} \frac{\partial}{\partial \mathbf{a}} \cdot [\mathbf{F}(s) f(\mathbf{a}, s)] \right) \right] \\
&= -\frac{\partial}{\partial \mathbf{a}} \cdot [\mathbf{F}(t) e^{-tL} f(\mathbf{a}, 0)] 
 + \frac{\partial}{\partial \mathbf{a}} \cdot \left[ \mathbf{F}(t) \int_0^t ds \, e^{-(t-s)L} \frac{\partial}{\partial \mathbf{a}} \cdot [\mathbf{F}(s) f(\mathbf{a}, s)] \right]
\end{aligned}
$$
得：
$$
\frac{\partial f(\mathbf{a}, t)}{\partial t} = -L f(\mathbf{a}, t) \\
 - \frac{\partial}{\partial \mathbf{a}} \cdot [\mathbf{F}(t) e^{-tL} f(\mathbf{a}, 0)] \\
 + \frac{\partial}{\partial \mathbf{a}} \cdot \left[ \mathbf{F}(t) \int_0^t ds \, e^{-(t-s)L} \frac{\partial}{\partial \mathbf{a}} \cdot [\mathbf{F}(s) f(\mathbf{a}, s)] \right]
$$

概率分布 $f(a,t)$ 平均值比上面的一般解更有统计意义。现在对上面方程取平均。


等式左边和右边第一项可直接取为$\frac{∂​⟨f(a,t)⟩}{∂t}$  和  $\frac{\partial}{\partial \mathbf{a}}​⋅\mathbf{v}(\mathbf{a})⟨f(\mathbf{a},t)⟩$   ;

第二项，初始分布函数 $f(a,0)$ 不受平均影响，且$⟨\mathbf{F}(t)⟩=0,$，所以此项取平均为 0 ,

第三项，包含两个显式噪声因子，$\mathbf{F}(t)$ 和 $\mathbf{F}(s)$  ，$⟨\mathbf{F}(t),\mathbf{F}(s)⟩=Bδ(t−s)$  ,  


第三项中$f(\mathbf{a},s)$隐含噪声因子，但不做贡献，原因如下:（进一步解释参见附录2)
		
$\mathbf{F}(t)$与$f(\mathbf{a},s)$中隐含的噪声因子配对，得到 δ(t−s′)，其中 s′<s。那么 t>s>s′，δ(t−s′)永远是0。
		
平均引入了一个因子 B，而 δ函数消除了算子 $e^{−(t−s)L}$。
得到的结果是平均分布函数 $⟨f(a,t)⟩$的**福克-普朗克方程**：
$$
\frac{∂​⟨f(\mathbf{a},t)⟩}{∂t}=− \frac{\partial}{\partial \mathbf{a}}​⋅\mathbf{v}(\mathbf{a})⟨f(\mathbf{a},t)⟩+ \frac{\partial}{\partial \mathbf{a}}⋅\mathbf{B}⋅ \frac{\partial}{\partial{\mathbf{a}}}​⟨f(\mathbf{a},t)⟩
$$




### 动力学变量方程  推导  广义朗之万方程
（默认在广义相空间中）


动力学变量方程 描述单个系统(动力学变量A)的演化，广义朗之万方程仅仅是其数学重排

##### 投影算子

通常系统所处的广义相空间是无限维希尔伯特空间。

感兴趣的子空间由**相关变量**张成。子空间的正交部分则由无关变量张成。

定义一个投影算子来表示**将一个任意变量投影到相关变量子空间的操作**：

给定任意集合 {$A_n$}(**每个元素A_j是个相关动力学变量/函数/向量**)，作用于**任意变量 B** 上的投影算子由下式明确给出：
$$
\mathbf{PB}=(\mathbf{B},\mathbf{A})⋅(\mathbf{A},\mathbf{A})^{-1}⋅\mathbf{A} \tag{8.18}
$$
这里的内积符号是个扩展定义，$\mathbf{A}$是函数组成的集合，也可理解为列向量组成的矩阵。B是单个函数或列向量。这里的内积括号(,)形式上尊重矩阵乘法，扩展成了矩阵向量的内积。


此公式中的符号顺序设计得易于在需要时添加下标：
$$
PB=\sum\limits_j\sum\limits_k(B,A_j​)((A,A)^{-1})_{jk}A_k\tag{8.19}
$$
如果变量 {A} 已经正交归一化，那么 (A,A) 就是单位矩阵。


##### 推导广义朗之万方程

从结论来看，广义朗之万方程（H. Mori, 1965），形式如下：
$$
 \frac{d}{dt}a(t)​=iΩa(t)−∫_0^tdsK(s)a(t−s)+F(t) \tag{8.20}
$$
与 非线性朗之万方程 类似 的是，由以下几项组成：

            保守项  ， 记忆项  ，随机项
            (势能项 ， 阻尼项  ， 耗散项)

其推导的起点仅仅是刘维尔方程决定的动力学变量方程，与 朗之万方程无关。

正因如此 其与朗之万方程类似的形式也可以为 福克普朗克方程 的 OU过程假设 提供部分支持。

或者说，在具体的应用场景，福克普朗克方程的推导，原本的OU过程假设 会被替换被 场景下具体的广义朗之万方程。

与前面推导的区别是前面的福克普朗克方程，没有纳入阻尼项或者记忆项:
$$
\frac{\partial \mathbf{a}}{\partial t}=\mathbf{v}(\mathbf{a})+\mathbf{F}(t)
$$
$$
\frac{\partial f}{\partial t} =- \frac{\partial}{\partial \mathbf{a}}(\mathbf{v}(\mathbf{a})f+\mathbf{F}(t)f)
$$
并定义类比的刘维尔算子   $\mathbf{L}f= \frac{\partial}{\partial \mathbf{a}}(\mathbf{v}(\mathbf{a})f)$

实际场景是：
$$\frac{\partial f}{\partial t} = - \frac{\partial}{\partial \mathbf{a}}\left( i\Omega \mathbf{a}f + \int_0^tK(s)\mathbf{a}(t-s)ds \cdot f +\mathbf{F}(t)\right)

$$
这里定义类比的刘维尔算子会将记忆项纳入：
$$
\mathbf{L}f= \frac{\partial}{\partial \mathbf{a}}(i\Omega \mathbf{a}f + \int_0^tK(s)\mathbf{a}(t-s)ds \cdot f )
$$
大致思路如此，这里就不继续推导 广义朗之万方程对应的 福克普朗克方程 了。




回到正题，现在开始推导广义朗之万方程，我们将刘维尔算符分为两部分：
$$
L=\mathbf{P}L+(\mathbf{I}−\mathbf{P})L \tag{8.21}
$$
接着，我们使用一个算符恒等式：（[[V1#投影拆解恒等式(8.22)]]）
$$
e^{tL}=e^{t(\mathbf{I}−\mathbf{P})L}+∫_0^t​dse^{(t−s)L}\mathbf{P}Le^{s(\mathbf{I}−\mathbf{P})L} \tag{8.22}
$$
此式可以通过直接微分或通过*取拉普拉斯变换并利用卷积定理间接验证*。

然后，我们将此恒等式两边作用于量 $(\mathbf{I}-\mathbf{{P}})LA$。在左边，我们得到：
$$
\begin{aligned}
e^{tL}(\mathbf{I}-\mathbf{{P}})LA&=e^{tL}LA−e^{tL}\mathbf{P}LA\\
&=\left(e^{tL}\frac{d A}{d t}+\frac{d e^{tL}}{d t}A\right)−e^{tL}(LA,A)⋅(A,A)^{-1}⋅A\\
&= \frac{d}{d t}e^{tL}A−e^{tL}(LA,A)⋅(A,A)^{-1}⋅A\\
&=\frac{d}{d t}A(t)−(LA,A)⋅(A,A)^{-1}⋅A(t)
\end{aligned}
$$
在最后一行，我们使用了 $A(t)=e^{tL}A$，并认识到内积是数字，可与算符 $e^{tL}$对易。

在右边，我们定义：
$$
F(t)=e^{t(\mathbf{I}-\mathbf{P})L}(\mathbf{I}-\mathbf{P})LA \tag{8.24}
$$
这项将成为朗之万方程中的“**噪声**”项。于是右边变为：
$$
\begin{aligned}
&F(t)+\left( \int_0^tdse^{(t-s)L}\mathbf{P}Le^{s(\mathbf{I}-\mathbf{P})L} \right)⋅(\mathbf{I-\mathbf{P}})LA\\
=&F(t)+\int_0^tdse^{(t-s)L}\mathbf{P}LF(s)\\
=&F(t)​+∫_0^t​dse^{(t−s)L}(LF(s),A)⋅(A,A)^{-1}⋅A\\
=&F(t)+∫_0^tds(LF(s),A)⋅(A,A)^{-1}⋅A(t−s)
\end{aligned} \tag{8.25}
$$
现在：
$$
\frac{d}{d t}A(t)−(LA,A)⋅(A,A)^{-1}⋅A(t)=F(t)+∫_0^tds(LF(s),A)⋅(A,A)^{-1}⋅A(t−s)
$$

最后，我们通过下式定义矩阵 Ω和 K：
$$
\begin{gather*}
iΩ=(LA,A)⋅(A,A)^{-1} \tag{8.26}\\

K(t)=−(LF(t),A)⋅(A,A)^{-1}\tag{8.27}
\end{gather*}
$$
如果所使用的内积使得 L是反厄米的，那么上式也可以写作：
$$
K(t)=(F(t),LA)⋅(A,A)^{-1}=(e^{t(\mathbf{I}-\mathbf{P})L}(\mathbf{I}-\mathbf{P})LA,LA)⋅(A,A)^{-1}\tag{8.28}
$$
这些形式化代数操作的结果是：
$$
\frac{d}{d t}A(t)=iΩ⋅A(t)−∫_0^t​dsK(s)⋅A(t−s)+F(t)
$$




## 一图流


![[Pasted image 20260514212303.png]]




#### 应用举例

![[Pasted image 20260514221910.png]]



#### 场景一：蛋白质折叠的“能量地形”（构型空间）

蛋白质是一条长长的氨基酸链，它会随机折叠成特定的三维结构。

- **状态空间**：不再是普通的三维欧几里得空间，而是这条多肽链的“构型空间”（由无数个描述键角、二面角和扭转角的内部坐标构成，维度高达数千甚至数万）。
    
- **朗之万方程：
    
    描述**单条多肽链**在溶剂（如水分子）撞击下的随机游走轨迹。在这里，溶剂的黏滞阻力不再是与速度成正比的简单摩擦力，而是一个带有**记忆核（Memory Kernel）的广义摩擦项**，同时伴随一个高度相关的随机涨落力。LE 能够精确刻画蛋白质如何在崎岖的能量地形中“借助”热涨落跳出局部极小值（错误折叠），继续向全局最小值（天然构象）探索。
    
- **福克-普朗克方程**：
    
    描述由海量相同蛋白质组成的**系综**在构型空间中的概率密度演化。FPE 将微观的随机碰撞转化为宏观的“概率流”，其稳态解直接给出了系统在热力学平衡时的**玻尔兹曼分布**。通过计算概率流的密度，科学家可以估算出蛋白质折叠的平均时间常数以及各态之间的转变速率。
    

#### 场景二：神经网络的决策动力学（膜电位空间）

单个神经元接收大量随机输入的突触信号，处于不断的膜电位起伏中，并决定是否发放脉冲。

- **状态空间**：通常由神经元的膜电位 V和恢复变量 u构成的二维相空间（如 FitzHugh-Nagumo 模型），或者更高维度的离子通道状态空间。
    
- **朗之万方程的作用**：
    
    建模**单个神经元**的膜电位如何受到背景突触噪声（随机涨落项）的驱动。由于细胞膜的时间常数极小，惯性项往往可以忽略（过阻尼极限），退化为一个纯粹的随机微分方程。LE 在此处是分析“随机共振”现象的核心工具——它揭示了为什么适量的噪声反而能提高神经元对微弱信号的检测灵敏度，并最终触发动作电位。
    
- **福克-普朗克方程的作用**：
    
    用于计算神经元群体的**首次通过时间分布**（First Passage Time）。当膜电位作为随机游走在达到阈值前，FPE 可以解析地给出电位值的概率密度随时间扩散的过程。这是计算神经科学中预测“大脑反应时间（Reaction Time）”和“决策速度”的绝对核心理论，它将微观的离子通道随机开闭与宏观的行为学延迟紧密联系起来。
    

#### 场景三：股票价格与市场情绪的演化（完全抽象的空间）

在量化金融中，资产价格的演化不遵循 deterministic 的物理定律，而是被建模为一种几何布朗运动。

- **状态空间**：股票的对数价格 lnS和时间 t构成的半无限空间（价格必须为正，故采用对数变换）。这里没有任何物理意义上的势能，只有描述财富分配的抽象流形。
    
- **朗之万方程的作用**：
    
    描述**单只股票（或单一资产组合）**的价格轨迹。这里的漂移项代表了资产的预期收益率（如无风险利率），而扩散项（随机项）则代表了市场突如其来的“黑天鹅”事件或群体情绪的随机波动。通过引入非线性的 LE（如含跳跃扩散过程的模型），宽客（Quant）们可以模拟出真实市场中观察到的“波动率聚类”和“尖峰肥尾”现象。
    
- **福克-普朗克方程的作用**：
    
    推导**期权定价公式**的数学基石。布莱克（Black）和舒尔斯（Scholes）正是通过求解对应于几何布朗运动的 FPE（即前向 Kolmogorov 方程），得到了著名的布莱克-舒尔斯偏微分方程。在金融语境下，FPE 描述的是在风险中性测度下，资产价格概率密度的演化，它不仅用于定价，更是对冲基金进行风险管理和组合优化（如计算 VaR，即风险价值）的底层逻辑。
    

#### 场景四：复杂网络上的疾病传播（离散图空间）

流行病学中，人群不再是均匀混合的流体，而是分布在错综复杂的社交网络节点上。

- **状态空间**：由每个人（节点）的健康状态构成的离散集合 {S,I,R}（易感、感染、恢复）。当节点数趋于无穷大时，可近似为一个连续的高维单纯复形或图拉普拉斯特征空间。
    
- **朗之万方程的作用**：
    
    描述**个体层面**的接触与传染过程。在离散网络中，这表现为一种“跳跃-扩散”朗之万方程，其中随机项模拟了个体间随机发生的有效接触（导致状态从 S 跳向 I），而摩擦项则代表了隔离政策或免疫接种带来的“恢复阻力”。它帮助流行病学家理解超级传播者事件（Superspreading events）是如何在微观层面上触发的。
    
- **福克-普朗克方程的作用**：
    
    实现从微观 Markov 链到宏观连续动力学的桥梁。通过在图拉普拉斯算子上进行连续近似（Mean-Field Limit），FPE 能够描述感染密度在整个网络上的概率通量。其最大的威力在于**计算临界阈值（即基本再生数 R0​）**：通过分析 FPE 对应的线性化算子的谱半径，可以精确预测在何种网络连接度下，零星病例会引发全系统的相变（即大流行爆发）。
    

---

### 💡 核心总结

无论是折叠的蛋白质、放电的神经元，还是波动的股价和蔓延的疫情，**朗之万方程**都在为你讲述一个个**“个体在混乱中挣扎与探索”**的故事；而**福克-普朗克方程**则站在更高的维度，冷静地描绘着**“群体概率分布如何流动与归趋”**的宏大图景。