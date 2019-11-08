# 遗传算法模版
用Python实现的遗传算法的**类模版**，可求解简单(多)变量的函数最优化问题。
## 依赖
**matplotlib**：用于绘图

**scipy**：用于求解染色体位数与变量的关系

## 开始
### 定义基本参数
``` python
generation = 200  # 迭代次数
population_size = 30  # 种群大小
bound_list = [[2, 12], [2, 12]]  # 变量上下界与个数
delta = 4  # 变量精度（小数点后;整数写0）
pc = 0.7  # 配对概率
pm = 0.01  # 变异概率
opt = "max"  # 目标函数要最大值还是最小值
```

### 定义目标函数


修改函数F(x)即可，x为变量数组，哪怕只有一个变量，也需用x[0]表示。同时要注意对应顺序，x[0] 对应变量 x1。以此类推。

``` python
def F(x):
    res = x[1] * math.sin(2 * math.pi * x[0]) + x[0] * math.cos(2 * math.pi * x[1])  # f(x) = x2*sin(2pi*x1) + x1*cos(2pi*x2) 
    res = x[0] + x[1] # f(x) = x1 + x2
    return res
```

### 执行迭代

``` python
    ga = GA(generation, population_size, pc, pm, bound_list, delta, opt)
    ga.main()
```

