Page 1

左上 (Top-Left): ME 6200 课程标题和讲义编号

课程名称：ME 6200: 机械工程师的数学方法 (Mathematical Methods for Mechanical Engineers)

讲义编号：Handout #20

主题：傅里叶级数、傅里叶积分、傅里叶变换 (FOURIER SERIES, FOURIER INTEGRAL, FOURIER TRANSFORM)

本讲义内容列表：

函数展开 (Expansion of Functions)

通过函数集的线性组合求级数和 (Series sum via Linear Combination of a Function Set)

傅里叶级数 (Fourier Series)

傅里叶级数展开 (Fourier Series Expansion)

在 WolframAlpha 或 Matlab 中绘制级数展开 (Plot of Series Expansion in WolframAlph or Matlab)

左下 (Bottom-Left): 傅里叶级数展开 (§17.3)

级数展开 (SERIES EXPANSION)：定义为将一个函数表示为其他函数集的线性组合。

在第17章中，这个函数集中的函数是相互正交的 (orthogonal)。这与第9章用正交向量集表示向量类似。

假设有一个函数集 {fn(x)}，其中整数 n (0 ≤ n ≤ ∞) 是函数集中的索引。

我们可以用 fn(x) 的线性组合来表示另一个函数 F(x)：

求和 (SUMMATION): F(x) = Σ [an * fn(x)] (从 n=1 到 ∞) (公式 1)

其中 an 是 fn(x) 的系数 (coefficient)。

傅里叶级数中的函数 (Functions in Fourier Series):

fn(x) = cos(nπx/L) (公式 2)

和/或 gn(x) = sin(nπx/L) (公式 3)

其中 0 ≤ n ≤ ∞。

特别地，f0(x) = 1 (常数项)，g0(x) = 0。

注意：gn(x) 可以通过 fn(x) 加上一个相位移 (phase shift) φ 来表示，即 fn(x - φ)。

图示： 展示了 n=1, 2, 3, 4 时 gn(x)=sin(nπx/L) 和 fn(x)=cos(nπx/L) 的图像（假设 L=π，所以是 sin(nx) 和 cos(nx)）。这些是构成傅里叶级数的基本函数（基函数）。

右上 (Top-Right): 在 WolframAlpha 中绘图

讲解如何在 WolframAlpha (一个在线计算知识引擎) 中绘制傅里叶级数中的 sin 和 cos 函数，即 fn(x) 或 gn(x)。

网站：https://www.wolframalpha.com/

示例：

如果 L=π，则 π/L = 1。

绘制单个函数：输入 sin(2*x) 可以绘制 n=2 的正弦函数。

绘制多个函数：输入 sin(n x), {n=1,4} 可以同时绘制 n=1, 2, 3, 4 的正弦函数。类似地，cos(n x), {n=1,4} 可以绘制对应的余弦函数。

右下 (Bottom-Right): 在 Matlab 中绘图

讲解如何在 Matlab 中绘制傅里叶 sin 和 cos 函数。

示例代码解释：

n=3; % function #：设置要绘制的函数索引 n=3。

X=-pi:(2*pi/100):pi; % Sets a range and intervals for x (as a vector)：创建一个 x 值的向量，范围从 -π 到 π，步长为 2π/100（共 101 个点）。这里假设 L=π。

f = sin(n*x);：计算 n=3 时的正弦函数值。

g = cos(n*x);：计算 n=3 时的余弦函数值。

figure(1)：创建一个新的图形窗口。

plot(x,f, 'r-',x,g, 'b-');：绘制 f(x)（红色实线 'r-'）和 g(x)（蓝色实线 'b-'）对 x 的图像。

xlabel('x');：设置 x 轴标签。

ylabel('f_n(x),g_n(x)');：设置 y 轴标签。

title(['# of terms, n=', num2str(n, '%d')]);：设置图像标题，动态显示当前的 n 值。num2str(n, '%d') 将整数 n 转换为字符串。

傅里叶级数展开 (§17.3) (续)

傅里叶声称任何 (any) 函数 F(x) 都可以写成 cos/sin 函数的组合。

傅里叶展开 (Fourier expansion):

F(x) = a0 + Σ [an * cos(nπx/L) + bn * sin(nπx/L)] (从 n=1 到 ∞) (公式 TB 17.5a)

a0, an, bn 称为傅里叶系数 (Fourier Coefficients)。

欧拉公式 (EULER FORMULA) (在傅里叶之前，欧拉给出了计算系数的公式)：

a0 = (1/(2L)) * ∫[F(x) dx] (从 -L 到 L) (公式 TB 17.5b)。这表示 F(x) 在 [-L, L] 上的平均值 (Average of F(x))。

an = (1/L) * ∫[F(x) * cos(nπx/L) dx] (从 -L 到 L) (公式 TB 17.5c)

bn = (1/L) * ∫[F(x) * sin(nπx/L) dx] (从 -L 到 L) (公式 TB 17.5d)

注意： 这个级数展开是在区间 -L ≤ x ≤ L 内对 F(x) 进行的。

重要假设： 这个展开 (公式 17.5a) 是一个周期函数。展开假设 F(x) 是一个周期为 2L 的周期函数。

历史背景： 所有推导和理论细节在1900年代早期完成。拉普拉斯（傅里叶的上司）曾对此表示怀疑。这个级数展开在科学和工程的许多领域都非常有用。

Page 2

左上 (Top-Left): 示例 17.3.1 (续) - 方波系数计算 (a0)

假设 F(x) 是一个如下图所示的方波 (square wave)，并且 L = π。

函数定义：

F(x) = 0, -L < x < 0

F(x) = 4, 0 < x ≤ +L

函数图像：在 (-π, 0) 区间值为 0，在 (0, π] 区间值为 4。注意 F(x=0) 未定义 (存在跳跃间断点)。

计算 a0 (使用公式 TB 17.5b，这里 L=π)：

a0 = (1/(2π)) * ∫[F(x) dx] (从 -π 到 π)

a0 = (1/(2π)) * [ ∫[F(x) dx] (从 -π 到 0) + ∫[F(x) dx] (从 0 到 π) ]

a0 = (1/(2π)) * [ ∫[0 dx] (从 -π 到 0) + ∫[4 dx] (从 0 到 π) ]

a0 = (1/(2π)) * [ 0 + [4x] (从 0 到 π) ] = (1/(2π)) * [4π - 0] = (4π)/(2π) = 2

所以 a0 = 2。

左下 (Bottom-Left): 示例 17.3.1 (续) - 方波系数计算 (an, bn)

计算 an (使用公式 TB 17.5c，L=π)：

an = (1/π) * ∫[F(x) * cos(nx) dx] (从 -π 到 π)

an = (1/π) * [ ∫[0 * cos(nx) dx] (从 -π 到 0) + ∫[4 * cos(nx) dx] (从 0 到 π) ]

an = (1/π) * [ 0 + 4 * ∫[cos(nx) dx] (从 0 到 π) ]

an = (4/π) * [ (1/n) * sin(nx) ] (从 0 到 π)

an = (4/(nπ)) * [ sin(nπ) - sin(0) ] = (4/(nπ)) * [ 0 - 0 ] = 0

所以 an = 0 对于所有 n ≥ 1。

计算 bn (使用公式 TB 17.5d，L=π)：

bn = (1/π) * ∫[F(x) * sin(nx) dx] (从 -π 到 π)

bn = (1/π) * [ ∫[0 * sin(nx) dx] (从 -π 到 0) + ∫[4 * sin(nx) dx] (从 0 到 π) ]

bn = (1/π) * [ 0 + 4 * ∫[sin(nx) dx] (从 0 到 π) ]

bn = (4/π) * [ (-1/n) * cos(nx) ] (从 0 到 π)

bn = (-4/(nπ)) * [ cos(nπ) - cos(0) ]

bn = (-4/(nπ)) * [ cos(nπ) - 1 ]

分析 cos(nπ)：

n=1, cos(π) = -1

n=2, cos(2π) = +1

n=3, cos(3π) = -1

... cos(nπ) = (-1)^n

bn = (-4/(nπ)) * [ (-1)^n - 1 ]

讨论 n 的奇偶性：

如果 n 是偶数 (n=2, 4, 6,...), (-1)^n = 1, 则 bn = (-4/(nπ)) * [ 1 - 1 ] = 0。

如果 n 是奇数 (n=1, 3, 5,...), (-1)^n = -1, 则 bn = (-4/(nπ)) * [ -1 - 1 ] = (-4/(nπ)) * [-2] = 8/(nπ)。

总结 bn: bn = 0 (n为偶数)，bn = 8/(nπ) (n为奇数)。

右上 (Top-Right): 在 WolframAlpha 中绘制解

讲解如何在 WolframAlpha 中绘制这个方波的傅里叶级数近似解。

语法示例：

2+(8/pi)*Sum [sin( (2*m-1)*x)/(2*m-1)], {m,1,3}：绘制包含前 3 个奇数项 (m=1, 2, 3 对应 n=1, 3, 5) 的近似。

2+(8/pi)*Sum [sin( (2*m-1)*x)/(2*m-1)], {m,1,20}：绘制包含前 20 个奇数项 (直到 n=39) 的近似。

这里用 m 作为求和索引，n = 2m-1 来表示奇数。{m, 1, N} 表示求和的项数范围。

右下 (Bottom-Right): 在 Matlab 中绘制解及吉布斯现象

示例 17.3.1 (方波) 结果汇总:

F(x) = a0 + Σ [ancos(nπx/L) + bnsin(nπx/L)]

将 a0=2, an=0, bn (奇数项) 代入，并令 n=2m-1 (m=1, 2, ...):

F(x) = 2 + Σ [ (8/((2m-1)π)) * sin((2m-1)πx/L) ] (从 m=1 到 ∞)

当 L=π 时: F(x) = 2 + (8/π) * Σ [ sin((2m-1)x) / (2m-1) ] (从 m=1 到 ∞)

Matlab 代码解释：

N=3; % Number of terms to use...：设置级数中要包含的项数 (m 的最大值)。

X=-pi:(2*pi/100):pi;：设置 x 向量。

F=ones(size(X))*2; % Sets a0...：初始化 F 向量，所有元素都等于 a0=2。ones(size(X)) 创建一个与 X 大小相同的全1向量。

for m=1:N ... end：循环 N 次，累加每一项。

F = F + (8/pi) * sin( (2*m-1)*X)/(2*m-1);：在循环中，将第 m 项加到 F 上。注意 Matlab 的向量化运算，sin(...) 和 / 会作用于 X 向量的每个元素。

figure(1); plot(X,F); xlabel('x'); ylabel('F(x)'); title(...)：绘图及添加标签。

图示分析：

展示了使用不同项数 N (N=2, 3, 5, 10, 50, 200) 时傅里叶级数的近似效果。

随着 N 增大，级数越来越接近原始方波。

吉布斯现象 (Gibbs Phenomenon): 在函数的不连续点 (跳跃点) 附近，傅里叶级数会出现过冲 (Overshoot) 现象。即使 N 趋于无穷大，这个过冲的峰值也不会消失，它会收敛到一个比函数实际跳跃高度约高出 9% 的值。

结论：欧拉曾担心吉布斯现象，但傅里叶是对的，级数在 N→∞ 时确实收敛 (在 L2 范数或逐点收敛意义下，除了不连续点)。

Page 3

左上 (Top-Left): ME 6200 课程标题和讲义编号

讲义编号：Handout #21

本讲义内容列表：

正交函数 (Orthogonal Functions)

正交函数集 (Set of Orthogonal Functions)

在正交级数展开中寻找系数 (Finding Coefficients in Orthogonal Series Expansion of Functions)

傅里叶级数的正交性 (Orthogonality of Fourier Series)

欧拉解系数的推导 (Derivation of Euler Solution for Coefficients)

施图姆-刘维尔问题和特征值-特征函数对 (Sturm Liouville Problem and Eigenvalue-Eigenfunction pairs)

左下 (Bottom-Left): 正交函数集 (§17.3.2)

回顾正交向量 (Chapter 9):

设 {e1, e2, ..., en} 是一个正交向量集。

它们的点积 (dot product) 满足：ei · ej = 0 (如果 i ≠ j), ei · ej ≠ 0 (如果 i = j)。

向量的线性组合表示：

向量 v = c1e1 + c2e2 + ... + cjej + ... + cnen

为了求系数 cj，将等式两边点乘 ej：

v · ej = (c1e1 + ... + cjej + ... + cn*en) · ej

利用正交性，等式右边只有一项非零：v · ej = cj * (ej · ej)

所以，系数 cj = (v · ej) / (ej · ej)。

类比到函数：

函数 f(x) 和 g(x) 在区间 [-L, L] 上正交 (orthogonal)，如果它们的内积 (inner product) 为零：

∫[f(x) * g(x) dx] (从 -L 到 L) = 0 (如果 f ≠ g)

∫[f(x) * f(x) dx] (从 -L 到 L) ≠ 0 (如果 f = g，且 f 非零)

假设 {g1(x), g2(x), ..., gn(x), ...} 是一个正交函数集。

我们想将函数 G(x) 展开为这个集合的线性组合：G(x) = Σ [cn * gn(x)] (从 n=1 到 ∞)。

寻找系数 cn：

将等式两边乘以 gj(x)：G(x) * gj(x) = Σ [cn * gn(x) * gj(x)]

对等式两边从 -L 到 L 积分：∫[G(x) * gj(x) dx] = ∫[ Σ [cn * gn(x) * gj(x)] ] dx

交换积分和求和：∫[G(x) * gj(x) dx] = Σ [ cn * ∫[gn(x) * gj(x) dx] ]

利用 gn(x) 的正交性，积分 ∫[gn(x) * gj(x) dx] 只有在 n=j 时非零。

所以，∫[G(x) * gj(x) dx] = cj * ∫[gj(x) * gj(x) dx]

系数 cj = ∫[G(x) * gj(x) dx] / ∫[gj(x) * gj(x) dx]。

这个公式是计算正交级数展开系数的核心。

右上 (Top-Right): 欧拉公式为何有效 (§17.3.2)

对于整数 m 和 n，以及周期函数 F(x) 在 [-L, L] 区间内，以下积分关系成立（这些是傅里叶基函数的正交性关系）：

TB Eqn (17.24a): ∫[cos(mπx/L) * cos(nπx/L) dx] (从 -L 到 L)

= 0 (如果 m ≠ n)

= L (如果 m = n ≠ 0)

= 2L (如果 m = n = 0)

TB Eqn (17.24b): ∫[sin(mπx/L) * sin(nπx/L) dx] (从 -L 到 L)

= 0 (如果 m ≠ n)

= L (如果 m = n ≠ 0)

= 0 (如果 m = n = 0，因为 sin(0)=0)

TB Eqn (17.24c): ∫[cos(mπx/L) * sin(nπx/L) dx] (从 -L 到 L)

= 0 (对于所有 m 和 n)

结论： 因此，函数集 {cos(nπx/L), sin(nπx/L)} 对于 n = 0, 1, ..., ∞ 是一个正交函数集 (ORTHOGONAL FUNCTION SET)。 这就是为什么可以用它们来展开函数，并且用内积（积分）来计算系数。

右下 (Bottom-Right): 绘图验证正交性

可以使用 WolframAlpha 或 Matlab 绘制函数乘积的图像来直观理解正交性。

引入归一化变量 X = x/L，则区间变为 -1 < X < 1，函数变为 cos(nπX), sin(mπX)。

绘图示例：

sin(n*pi*X)*cos(m*pi*X)

cos(n*pi*X)*cos(m*pi*X)

sin(n*pi*X)*sin(m*pi*X)

建议尝试不同的 m, n 组合来观察积分（即曲线下的面积）是否为零。

WolframAlpha 示例： plot[sin(1*pi*x)*cos(2*pi*x)], {x,-1,1}。观察图像关于 y 轴是否对称或反对称，以及在 [-1, 1] 上的总面积。

Page 4

左上 (Top-Left): 欧拉公式为何有效 (§17.3.2) - 图示 (m≠n)

用图形展示当 m ≠ n 时正交积分的结果。

示例 (n=1, m=2):

cos(πx/L) * cos(2πx/L)：绘制此函数图像。观察到在一个周期内，正负面积相互抵消，总积分（总面积）为 0。对应 Eq 17.24a (m≠n)。图中用 +A1, -A1 等表示面积块。

sin(πx/L) * sin(2πx/L)：绘制此函数图像。同样观察到正负面积抵消，总积分为 0。对应 Eq 17.24b (m≠n)。

cos(πx/L) * sin(2πx/L) 或 cos(2πx/L) * sin(πx/L)：绘制此函数图像。也观察到正负面积抵消，总积分为 0。对应 Eq 17.24c。

结论： 图形直观地显示了当 m≠n 时，基函数的乘积在一个周期 [-L, L] 上的积分为零。

左下 (Bottom-Left): 欧拉公式为何有效 (§17.3.2) - 图示 (m=n)

用图形展示当 m = n 时的情况。

示例 (n=1, m=1) 和 (n=2, m=2):

cos(nπx/L) * cos(nπx/L) = cos^2(nπx/L)：绘制 cos^2(πx/L) 和 cos^2(2πx/L)。图像始终在 x 轴上方（或触及 x 轴），因此积分（面积）大于 0。对应 Eq 17.24a (m=n≠0)。总面积 > 0。

sin(nπx/L) * sin(nπx/L) = sin^2(nπx/L)：绘制 sin^2(πx/L) 和 sin^2(2πx/L)。图像也始终在 x 轴上方（或触及 x 轴），积分大于 0。对应 Eq 17.24b (m=n≠0)。总面积 > 0。

cos(nπx/L) * sin(nπx/L)：绘制 cos(πx/L)sin(πx/L) 和 cos(2πx/L)sin(2πx/L) (即 (1/2)sin(2nπx/L))。图像在一个周期内正负面积仍然相互抵消，总积分等于 0。对应 Eq 17.24c。总面积 = 0。

右上 (Top-Right): 欧拉公式推导 (§17.3.2) - bn 系数

目标： 推导 bn 的计算公式。

步骤：

写出傅里叶展开式：F(x) = a0 + Σ [ancos(nπx/L) + bnsin(nπx/L)] (TB 17.5a)

将等式两边乘以 sin(mπx/L)，其中 m 是某个正整数：
F(x)sin(mπx/L) = a0sin(mπx/L) + Σ [ancos(nπx/L)sin(mπx/L) + bnsin(nπx/L)sin(mπx/L)]

对等式两边从 -L 到 L 积分：
∫[F(x)sin(mπx/L) dx] = ∫[a0sin(mπx/L) dx] + Σ [ an∫[cos(nπx/L)sin(mπx/L) dx] + bn∫[sin(nπx/L)sin(mπx/L) dx] ]

应用正交关系：

∫[a0sin(mπx/L) dx] = 0 (因为 sin 是奇函数，关于原点对称积分)。

∫[cos(nπx/L)sin(mπx/L) dx] = 0 (根据 Eq 17.24c)。

∫[sin(nπx/L)sin(mπx/L) dx] = 0 (如果 n ≠ m) 或 L (如果 n = m ≠ 0) (根据 Eq 17.24b)。

求和 Σ 中，只有当 n = m 时，bn 后面的积分项才不为零，其值为 L。

因此，等式变为：∫[F(x)sin(mπx/L) dx] = bm * L。

解出 bm：bm = (1/L) * ∫[F(x)sin(mπx/L) dx] (这与 TB 17.5d 一致)。

特殊情况： 如果 n=0，sin(0)=0，所以 bn 不涉及 n=0 的情况。如果 m=n=0，积分为0（无用）。

结论：利用正交性可以分离出特定的系数 bn。

右下 (Bottom-Right): 欧拉公式推导 (§17.3.2) - a0 和 an 系数

目标： 推导 a0 和 an 的计算公式。

步骤 (求 an, m>0):

将傅里叶展开式两边乘以 cos(mπx/L) (m > 0)。

F(x)cos(mπx/L) = a0cos(mπx/L) + Σ [ancos(nπx/L)cos(mπx/L) + bnsin(nπx/L)cos(mπx/L)]

对等式两边从 -L 到 L 积分。

应用正交关系：

∫[a0cos(mπx/L) dx] = 0 (m>0 时 cos 在对称区间积分为0)。

∫[sin(nπx/L)cos(mπx/L) dx] = 0 (根据 Eq 17.24c)。

∫[cos(nπx/L)cos(mπx/L) dx] = 0 (如果 n ≠ m) 或 L (如果 n = m ≠ 0) (根据 Eq 17.24a)。

求和 Σ 中，只有当 n = m 时，an 后面的积分项才不为零，其值为 L。

因此，等式变为：∫[F(x)cos(mπx/L) dx] = am * L。

解出 am：am = (1/L) * ∫[F(x)cos(mπx/L) dx] (这与 TB 17.5c 一致)。

步骤 (求 a0, m=0):

直接对傅里叶展开式两边从 -L 到 L 积分 (相当于乘以 cos(0πx/L) = 1)：
∫[F(x) dx] = ∫[a0 dx] + Σ [ an∫[cos(nπx/L) dx] + bn∫[sin(nπx/L) dx] ]

应用积分性质/正交关系：

∫[a0 dx] (从 -L 到 L) = a0 * [x] (从 -L 到 L) = a0 * (L - (-L)) = 2L * a0。

∫[cos(nπx/L) dx] = 0 (对于 n ≥ 1)。

∫[sin(nπx/L) dx] = 0 (对于 n ≥ 1)。

因此，等式变为：∫[F(x) dx] = 2L * a0。

解出 a0：a0 = (1/(2L)) * ∫[F(x) dx] (这与 TB 17.5b 一致)。

结论：利用正交性（以及常数函数的特殊性）可以分离出系数 a0 和 an。

Page 5

左上 (Top-Left): 记号 (§17.6) 和 导数

函数运算：

f + g = f(x) + g(x)

af = a * f(x) (a 是标量)

-f = -f(x)

f + (-f) = 0

内积 (INNER PRODUCT):

<f|g> (狄拉克 Bra-Ket 记号) = ∫[f(x) * g(x) dx] (从 a 到 b)。这里区间变为 [a, b]。

等价于记号 (f, g)。

示例： <sin(nπx/L)|sin(nπx/L)> = ∫[sin^2(nπx/L) dx] (从 -L 到 L) = L (对于 n > 0)。

正交性： 如果 <f|g> = 0，则 f(x) 和 g(x) 正交。

示例： <sin(nπx/L)|cos(mπx/L)> = ∫[sin(nπx/L)cos(mπx/L) dx] (从 -L 到 L) = 0。

范数 (NORM): ||f|| = ||f(x)|| = √<f|f> = √(∫[f(x)^2 dx])。

示例： ||sin(nπx/L)|| = √(<sin|sin>) = √L (对于 n > 0)。

导数记号：

x: 自变量 (independent variable)

f(x): 因变量 (dependent variable)

f' = f'(x) = d/dx f(x)：f 对 x 的一阶导数，表示 f 随 x 变化的响应或变化率。

f'' = f''(x) = d/dx [f'(x)] = d^2/dx^2 f(x)：f 对 x 的二阶导数，表示 f' 随 x 变化的响应或变化率。

左下 (Bottom-Left): 常微分方程 (ODE) (回顾第3章)

ODE 定义： 包含一个单自变量函数 f(x) 及其导数 (f', f'', f''' 等) 的方程。

示例： (f''')^2 - 2xf'f'' = sin x

线性 ODE (Linear ODE): 方程中 f(x) 及其所有导数仅乘以自变量的函数，而不乘以其他 f 的导数或 f 本身。

示例： sin(x) * f''' - √x * f'' - 5f' + x^2 * f = g(x)。这是一个 3 阶线性 ODE。

如果 g(x) = 0，则为齐次 (HOMOGENEOUS) ODE。

如果 g(x) ≠ 0，则为非齐次 (NON-HOMOGENEOUS) ODE。

ODE 的阶 (ORDER): 方程中出现的最高阶导数的阶数。

ODE vs PDE: ODE 只有一个自变量。多个自变量的微分方程称为偏微分方程 (PDE - Partial Differential Equations)。

定理： n 阶 ODE 的最一般解 (Most GENERAL SOLUTION) 是 n 个线性无关函数的线性组合 (L.C. - Linear Combination)。

例如：1 阶 ODE 的通解由一个独立函数满足。

2 阶 ODE 的通解是两个独立解的线性组合。

3 阶 ODE 的通解是三个独立解的线性组合。

右上 (Top-Right): 施图姆-刘维尔问题 (§17.7.1)

给定： 实值函数 p(x)>0, q(x), w(x)>0 在区间 a ≤ x ≤ b 上，以及实值系数 α, β, γ, δ。

施图姆-刘维尔问题 (Sturm-Liouville Problem, SLP): 寻找满足以下二阶线性齐次 ODE 和边界条件 (BCs) 的所有函数 Φn(x) (特征函数) 和对应的常数 λn (特征值)。

SLP ODE 标准形式: d/dx [p(x) * df/dx] + q(x)f(x) = -λw(x)f(x)

齐次边界条件 (Homogeneous BCs):

在 x=a 处： αf(a) + βf'(a) = 0

在 x=b 处： γf(b) + δf'(b) = 0

另一种记法： [p(x)f']' + q(x)f = -λw(x)f

核心任务： 找到所有满足 ODE 和 BCs 的特征函数-特征值对 {Φn(x), λn}。

Φn(x) 是第 n 个特征函数 (EIGENFUNCTION)。

λn 是第 n 个特征值 (EIGENVALUE)。

展开 ODE: p(x)f'' + p'(x)f' + [q(x) + λw(x)]f = 0。这是一个线性齐次 (LINEAR ODE, HOMOGENEOUS) ODE。

右下 (Bottom-Right): 示例 17.7.1 (特征函数和特征值)

给定问题：

ODE: f'' + λf = 0, 0 < x < L

BCs: f(0) = 0, f(L) = 0

与 SLP 标准形式比较： f'' = -λf

这里 [1 * f']' + 0f = -λ1*f

所以 p(x) = 1 (>0), q(x) = 0, w(x) = 1 (>0)。区间是 [0, L]。

BC1: f(0) = 0 => α=1, β=0 (1f(0) + 0f'(0) = 0)。

BC2: f(L) = 0 => γ=1, δ=0 (1f(L) + 0f'(L) = 0)。

求解：

ODE 的通解形式为 f(x) = Acos(kx) + Bsin(kx)，其中特征方程是 r^2 + λ = 0，所以 r = ±i√λ。令 k = √λ (假设 λ > 0)。

应用 BC 1 (f(0)=0): Acos(0) + Bsin(0) = 0 => A1 + B0 = 0 => A = 0。

现在解为 f(x) = B*sin(kx)。

应用 BC 2 (f(L)=0): B*sin(kL) = 0。

如果 B = 0，则 f(x) = 0，这是平凡解 (trivial solution)，通常不感兴趣。

为了得到非平凡解 (B≠0)，必须有 sin(kL) = 0。

sin(θ) = 0 的解是 θ = nπ，其中 n 是整数。

所以 kL = nπ => k = nπ/L，其中 n = ±1, ±2, ... (n=0 会导致 k=0, λ=0，下面单独讨论。sin(-θ)=-sin(θ)，所以负的 n 只是改变了 B 的符号，可以合并)。

因此，特征值 λn = k^2 = (nπ/L)^2，对于 n = 1, 2, 3, ...

对应的特征函数 Φn(x) = B*sin(nπx/L)。通常将 B 归一化为 1，所以 Φn(x) = sin(nπx/L)。

检查 λ=0 的情况：

ODE 变为 f'' = 0。

通解为 f(x) = Cx + D。

BC1: f(0) = C*0 + D = 0 => D = 0。

BC2: f(L) = CL + D = CL + 0 = 0 => C = 0 (因为 L≠0)。

所以 λ=0 只导致平凡解 f(x)=0。因此，λ=0 不是这个问题的特征值。

Page 6

左上 (Top-Left): ME 6200 课程标题和讲义编号

讲义编号：Handout #22

本讲义内容列表：

带权函数的内积 (Inner product with a weight function, w(x))

施图姆-刘维尔定理 (Sturm Liouville Theorem, SLT)

SLP 的正交特征函数 (Orthogonal Eigenfunctions of SLP)

SLP 特征函数的唯一、简单和正特征值 (Unique, Simple and positive Eigenvalues of SLP Eigenfunctions)

使用 SLP 特征函数的级数展开的收敛性 (Convergence of series expansion with SLP Eigenfunctions)

左下 (Bottom-Left): 施图姆-刘维尔定理 (17.7.1)

重新定义内积 (REDEFINE INNER PRODUCT):

<f|g> = ∫[f(x) * g(x) * w(x) dx] (从 a 到 b)。

这里的 w(x) 与 SLP 中的权函数 (weight function) 相同。

正交性：

给定整数 m ≠ n，以及对应的 SLP 特征值 λm ≠ λn。

结论：对应的特征函数 Φn 和 Φm 关于权函数 w(x) 正交。

即 <Φn|Φm> = ∫[Φn(x) * Φm(x) * w(x) dx] = 0 (如果 m ≠ n)。

<Φn|Φn> = ∫[Φn(x)^2 * w(x) dx] ≠ 0。

结论： SLP 的特征函数集 {Φn(x)} 构成了一个正交集 (orthogonal set) (在包含权函数 w(x) 的内积定义下)。

用特征函数展开 y(x):

y(x) = Σ [Cn * Φn(x)] (从 n=1 到 ∞)。

系数 Cn 的计算公式：Cn = <y|Φn> / <Φn|Φn>

Cn = (∫[y(x) * Φn(x) * w(x) dx]) / (∫[Φn(x)^2 * w(x) dx])

右上 (Top-Right): 施图姆-刘维尔定理 (Theorem 17.7.1) 的性质

设 λn 是 SLP 的任意特征值，Φn(x) 是对应的特征函数。

性质：

a) λn 是实数 (real)。 (√)

b) λn 是简单的 (simple)，即每个特征值 λn 只对应一个（除了常数倍）线性无关的特征函数 Φn(x)。 (√)

c) 特征值 λn 有无穷多个，可以排序 λ1 < λ2 < λ3 < ...，并且当 n → ∞ 时，λn → ∞。(√)

d) 特征函数 Φn 是正交的 (关于权函数 w(x))。(√)

e) 展开收敛性 (Expansion Convergence): 级数 Σ [Cn * Φn(x)] (其中 Cn = <f|Φn>/<Φn|Φn>)

收敛到 f(x) （如果在 x 点连续）。

收敛到 [f(x-) + f(x+)] / 2 （如果在 x 点不连续，即左右极限的平均值）。

前提条件：f 和 f' 在 [a, b] 上分段连续。

f) 误差减小 (Error gets smaller): 当级数求和的项数 N 增加时，近似误差减小。(√)

回顾示例 17.1.1 (方波的正弦级数展开):

特征值 λn = (nπ/L)^2 (n=1, 2,...) 都是实数 (a)。

每个 λn 只对应 sin(nπx/L) (b)。

有无穷多个 λn，按 n^2 排序，趋于无穷 (c)。

sin(nπx/L) 相互正交 (w(x)=1) (d)。

傅里叶级数收敛到方波 (在间断点收敛到跳跃中点 (2)) (e)。图示了 m_max=5 和 m_max=50 的近似情况，N 越大越接近。

随着项数增加，近似效果更好 (f)。

右下 (Bottom-Left): 示例 17.7.2 (SL 展开)

问题： 用示例 17.7.1 的特征值和特征函数展开函数 f(x) = x，在 0 ≤ x ≤ L 区间上。

已知：

λn = (nπ/L)^2

Φn(x) = sin(nπx/L)

w(x) = 1 (来自 Ex 17.7.1)

目标： 找到级数展开 yN(x) = Σ [Cn * Φn(x)] (从 n=1 到 N) 来近似 f(x)=x。 (公式 1)

Φn 是 w(x)=1 时的解。 (公式 2)

计算系数 Cn: Cn = <f|Φn> / <Φn|Φn> (公式 3)

分母 <Φn|Φn>: ∫[sin^2(nπx/L) * 1 dx] (从 0 到 L) = L/2。(注意这里积分区间是 [0, L]，不是 [-L, L]，但结果仍是 L/2)。

分子 <f|Φn>: ∫[x * sin(nπx/L) * 1 dx] (从 0 到 L)

使用分部积分法 (∫udv = uv - ∫vdu)：u=x, dv=sin(nπx/L)dx => du=dx, v=(-L/nπ)cos(nπx/L)

∫ = [x * (-L/nπ)cos(nπx/L)] (从 0 到 L) - ∫[(-L/nπ)cos(nπx/L) dx] (从 0 到 L)

= [(-L^2/nπ)cos(nπ) - 0] + (L/nπ) * [(L/nπ)sin(nπx/L)] (从 0 到 L)

= (-L^2/nπ) * (-1)^n + (L/nπ) * [(L/nπ)sin(nπ) - 0]

= L^2/(nπ) * (-1)^(n+1)

Cn = [ L^2/(nπ) * (-1)^(n+1) ] / [ L/2 ] = (2L / nπ) * (-1)^(n+1) (公式 3 →)

展开式 yn(x): yn(x) = Σ [(2L / nπ) * (-1)^(n+1) * sin(nπx/L)] (从 n=1 到 N) (公式 4)

误差 en(x): en(x) = yN(x) - f(x) (公式 5)

图示： 展示了 N=3 和 N=10 时，近似解 y(x)/L 和误差 e(x)/L 随 x/L 的变化。可以看到随着 N 增加，误差减小 (E 和 e_max 减小)。

Page 7

左上 (Top-Left): 示例 17.7.3 (不同于 17.7.1 的边界条件)

给定问题：

ODE: f'' + λf = 0, 0 < x < L=1

BCs: f(0) - 2f'(0) = 0, f(L) = 0

与 SLP 比较： ODE 形式 f'' = -λf，表明 p(x)=1, q(x)=0, w(x)=1。

求解：

通解: f(x) = Acos(kx) + Bsin(kx)，其中 k^2 = λ。

f'(x) = -Aksin(kx) + Bkcos(kx)。

应用 BC 1 (x=0): f(0) - 2f'(0) = 0

f(0) = A

f'(0) = Bk

A - 2(Bk) = 0 => A = 2Bk (公式 3)

应用 BC 2 (x=L=1): f(L) = f(1) = 0

Acos(k) + Bsin(k) = 0 (公式 4)

将 A = 2Bk 代入公式 4:

(2Bk)cos(k) + Bsin(k) = 0

B * [2k*cos(k) + sin(k)] = 0

为了得到非平凡解 (B≠0)，必须有 2k*cos(k) + sin(k) = 0。

整理得到 tan(k) = -2k (公式 5)。这是一个特征方程 (eigenvalue equation)，它的解 k 值决定了特征值 λ = k^2。

求解特征方程：

这是一个超越方程，通常需要数值或图形方法求解。

图形法： 绘制 y = tan(k) (LHS) 和 y = -2k (RHS) 的图像。它们的交点对应的 k 值就是解。

图示分析： 绘制了 tan(k) 和 -2k 关于 k/π (k) 的图像。可以看到一系列的交点 k1, k2, k3, ...

计算特征值：

k1 ≈ 0.5846π => λ1 = k1^2 ≈ 3.3731

k2 ≈ 1.5329π => λ2 = k2^2 ≈ 23.1923

k3 ≈ 2.5201π => λ3 = k3^2 ≈ 62.6797

渐近行为： 当 n → ∞ 时，tan(kn) = -2kn。由于 tan 函数在 (n-1/2)π 处趋于无穷，kn 必须接近 (n-1/2)π。更精确地，kn ≈ (n - 1/2)π。所以 √λn ≈ (n - 1/2)π => λn ≈ (π^2/4) * (2n - 1)^2。

左下 (Bottom-Left): 示例 17.7.2 (SL 展开) - 误差分析

误差度量：

总误差 (Total Error): EN = ∫[en(x) dx] (从 0 到 L)。(这个度量可能不太常用，因为正负误差会抵消)。

均方根误差 (RMS Error): ERMS = √[ (1/L) * ∫[en(x)^2 dx] (从 0 到 L) ] = √[ <en|en> / L ]。(这是更常用的度量)。

图示：

展示了 N=50, 200, 500 时 y(x)/L 和 e(x)/L 的图像，显示了随着 N 增加，近似越来越好，误差越来越小。

总误差 vs N 图： EN 随 N 增加而减小（波动）。

RMS 误差 vs N 图 (log-log scale): ERMS 随 N 增加而显著减小，近似一条直线，表明误差随 N 按幂律下降。

结论： 这些图验证了 定理 17.1.1(f)：当 N 增加时，误差减小。

右上 (Top-Right): 特征方程求解 - 矩阵方法

将两个边界条件的代数方程 (3) A = 2Bk 和 (4) Acos(kL) + Bsin(kL) = 0 (L=1) 组合起来，看作关于 A 和 B 的线性方程组：

1A - 2kB = 0

cos(kL)*A + sin(kL)*B = 0

写成矩阵形式： [ [1, -2k], [cos(kL), sin(kL)] ] * [A, B]^T = [0, 0]^T

为了使这个齐次线性方程组有非零解 (A, B 不全为零)，系数矩阵的行列式 (Determinant) 必须为零：

det = 1 * sin(kL) - (-2k) * cos(kL) = 0

sin(kL) + 2k*cos(kL) = 0

这与之前得到的 tan(kL) = -2k 是等价的（假设 cos(kL)≠0）。

结论： 求解特征值问题等价于寻找使得系数矩阵行列式为零的 k (或 λ) 值。这是一种找到特征方程的系统方法。

右下 (Bottom-Right): 使用 WolframAlpha 查找根

提供了一些 WolframAlpha 的代码示例来查找特征方程 tan(k) + 2k = 0 的根。

绘图函数 (Plot):

Plot[ { Tan[k], -2*k }, {k, 0, 10}]：同时绘制 tan(k) 和 -2k，观察交点。{k, 0, 10} 指定绘图范围。

Plot[ { Tan[k] + 2*k == 0 }, {k, 0, 10}]：直接绘制满足方程的点。

plot tan(k)+2*k==0, k,1,10：更简洁的语法，同时给出根的近似值。

查找根函数 (FindRoot):

FindRoot[ { Tan[k] + 2*k == 0 }, {k, 1.8} ]：从初始猜测值 k=1.8 开始，数值求解第一个正根。

FindRoot[ { Tan[k] + 2*k == 0 }, {k, 4.8} ]：从初始猜测值 k=4.8 开始，求解第二个正根。

FindRoot[ { Tan[k] + 2*k == 0 }, {k, 7.9} ]：从初始猜测值 k=7.9 开始，求解第三个正根。

注意： FindRoot 需要一个初始猜测值 (Initial Guess)，并且只会找到离猜测值最近的一个根。

Page 8

左上 (Top-Left): 示例 17.7.3 (续) - 特征函数和展开

特征函数：

我们有 A = 2Bk，其中 k = kn 是 tan(k) = -2k 的解，λn = kn^2。

f(x) = Acos(kx) + Bsin(kx) = 2Bkcos(kx) + Bsin(kx) = B * [2k*cos(kx) + sin(kx)]

令 B=1，得到第 n 个特征函数：Φn(x) = 2√λn * cos(√λn * x) + sin(√λn * x) （因为 k=√λn）。

这些 Φn(x) 构成一个正交集 (因为它们是 SLP 的解，w(x)=1)。

齐次 ODE 的解： y(x) = Σ [an * Φn(x)] (n=1 to ∞)，其中 an 是任意常数。

用特征函数展开已知函数 g(x):

g(x) = Σ [Cn * Φn(x)] (n=1 to ∞)

系数 Cn = <g|Φn> / <Φn|Φn> = (∫[g(x)Φn(x)1 dx]) / (∫[Φn(x)^21 dx]) (积分区间 [0, L])

关于 λ=0： 在 Ex 17.7.3 中，如果 λ=0 (k=0)，f=Ax+B。BC1: A-2B=0 (A=2B)。BC2: f(L)=AL+B=0 => 2BL+B=B(2L+1)=0。因为 L=1>0，所以 B=0，进而 A=0。λ=0 仍然只导致平凡解，不是特征值。

左下 (Bottom-Left): 示例 17.7.4 (带 f' 项的 ODE)

给定问题：

ODE: f'' - 2f' + λf = 0, 0 < x < π (公式 1)

BCs: f(0) = 0, f(π) = 0 (公式 2)

问题： 这个 ODE 不是标准的 SL 形式 ([pf']'+qf=-λwf)。

目标： 将其转换为 SL 形式。

方法： 乘以一个积分因子 (integrating factor) σ(x)，使得 σf'' - 2σf' + λσf = 0 (公式 5) 能够写成 [p(x)f']' + ... 的形式。

回忆 [p(x)f']' = p(x)f'' + p'(x)f' (公式 3)。

比较 σf'' - 2σf' 和 p(x)f'' + p'(x)f'：

需要 p(x) = σ(x)

需要 p'(x) = -2σ(x)

即 σ'(x) = -2σ(x)。这是一个一阶线性 ODE。

解得 σ(x) = C * e^(-2x)。取 C=1，所以积分因子 σ(x) = e^(-2x)。

转换后的 ODE:

用 e^(-2x) 乘以原始 ODE (1)：e^(-2x)f'' - 2e^(-2x)f' + λe^(-2x)f = 0 (公式 4 → 6)

注意到前两项正好是 (e^(-2x)f')'。

所以 ODE 变为 (e^(-2x) f')' + λe^(-2x) f = 0 (公式 6)。

SL 形式确认：

与 [p(x)f']' + q(x)f = -λw(x)f 比较 (注意符号!)。这里似乎写成了 +λwf 的形式。如果标准形式是 [pf']'+qf+λwf=0，那么：

p(x) = e^(-2x) (>0)

q(x) = 0

w(x) = e^(-2x) (>0)

所以现在 ODE 是 SL 形式了。

下一步： 求解这个 SLP 的特征值和特征函数。

尝试解形式： φ(x) = e^(rx)。代入原始 ODE (1): r^2e^(rx) - 2re^(rx) + λ*e^(rx) = 0。

特征方程：r^2 - 2r + λ = 0。

解：r = [2 ± √(4 - 4λ)] / 2 = 1 ± √(1 - λ)。

考虑 BCs (φ(0)=0, φ(π)=0): 为了满足这两个 BC，解需要是振荡的（三角函数），这要求根是复数。因此，1 - λ < 0 => λ > 1。

令 1 - λ = -k^2 (k>0)，则 λ = 1 + k^2。

根为 r = 1 ± ik。

通解形式为 φ(x) = e^x * [Ccos(kx) + Dsin(kx)] (公式 7)。

应用 BC 1 (φ(0)=0): e^0 * [Ccos(0) + Dsin(0)] = 0 => 1 * [C1 + D0] = 0 => C = 0。

解变为 φ(x) = De^xsin(kx)。

应用 BC 2 (φ(π)=0): De^πsin(kπ) = 0。

为了非平凡解 (D≠0)，必须有 sin(kπ) = 0。

所以 kπ = nπ，其中 n = 1, 2, 3, ... (n=0 导致 k=0, λ=1，此时解为 De^x*0=0，平凡解)。

因此 k = n。

特征值： λn = 1 + k^2 = 1 + n^2 (n=1, 2, 3, ...) (公式 8.b)。

特征函数： Φn(x) = De^xsin(nx)。取 D=1， Φn(x) = e^x * sin(nx) (公式 8.a)。

右上 (Top-Right): 示例 17.7.4 (续) - 展开与正交性

用特征函数展开 g(x): g(x) = Σ [Cn * Φn(x)] = Σ [Cn * e^x * sin(nx)] (公式 9)。

计算系数 Cn: Cn = <g|Φn> / <Φn|Φn> (公式 10)。

重要： 这里的内积必须使用权函数 w(x) = e^(-2x)。

分母 <Φn|Φn>: ∫[Φn(x)^2 * w(x) dx] (从 0 到 π)

= ∫[(e^x * sin(nx))^2 * e^(-2x) dx] = ∫[e^(2x) * sin^2(nx) * e^(-2x) dx]

= ∫[sin^2(nx) dx] (从 0 到 π) = π/2。

分子 <g|Φn>: ∫[g(x) * Φn(x) * w(x) dx] (从 0 到 π)

= ∫[g(x) * (e^x * sin(nx)) * e^(-2x) dx]

= ∫[g(x) * e^(-x) * sin(nx) dx] (从 0 到 π)。

Cn = (2/π) * ∫[g(x) * e^(-x) * sin(nx) dx] (从 0 到 π) (公式 10 →)。

正交性验证：

特征函数 Φn(x) = e^x*sin(nx) 应该是关于权函数 w(x)=e^(-2x) 正交的。

<Φn|Φm> = ∫[Φn(x) * Φm(x) * w(x) dx] (从 0 到 π)

= ∫[(e^x sin(nx)) * (e^x sin(mx)) * e^(-2x) dx]

= ∫[sin(nx) * sin(mx) dx] (从 0 到 π)

根据标准三角函数正交性，这个积分在 n ≠ m 时等于 0。得证。

警告： 如果在计算内积时忽略权函数 w(x) (即令 w(x)=1)，那么：

∫[Φn(x) * Φm(x) * 1 dx] = ∫[(e^x sin(nx)) * (e^x sin(mx)) dx] = ∫[e^(2x) * sin(nx) * sin(mx) dx]

这个积分在 n ≠ m 时不等于 0。

结论： 使用错误的内积（不含权函数）会导致函数集看起来不正交，并且无法正确计算展开系数。对于 SLP 问题，必须使用由 w(x) 定义的加权内积。

右下 (Bottom-Right): 总结

我们需要正交函数来进行级数展开（以便容易地计算系数）。

施图姆-刘维尔问题产生的特征函数关于权函数 w(x) 正交。

因此，在处理 SLP 的特征函数展开时，必须使用包含正确权函数 w(x) 的内积来计算系数 Cn。

Page 9

左上 (Top-Left): ME 6200 课程标题和讲义编号

讲义编号：Handout #23

本讲义内容列表：

周期性 SLP (Periodic SLP's)

奇异 SLP 及其在边界处的奇异性含义 (Singular SLP's and Implications of Singularity at the Boundaries)

傅里叶-贝塞尔级数 (Fourier-Bessel Series)

傅里叶-勒让德级数 (Fourier-Legendre Series)

左下 (Bottom-Left): 周期性 SLP (§17.8)

回顾 SLP ODE: [p(x)f']' + q(x)f = -λw(x)f, a ≤ x ≤ b。

修改边界条件为周期性边界条件 (Periodic Boundary Conditions):

f(a) = f(b)

f'(a) = f'(b)

示例： 回顾 Ex 17.1.1 的 ODE: f'' + λf = 0, 在区间 -L < x < L 上。

这里 p(x)=1, q(x)=0, w(x)=1。

应用周期性 BCs:

BC 1: f(-L) = f(L)

BC 2: f'(-L) = f'(L)

通解： φ(x) = Acos(kx) + Bsin(kx) (k^2=λ)

φ'(x) = -Aksin(kx) + Bkcos(kx)

应用 BC 1: Acos(-kL) + Bsin(-kL) = Acos(kL) + Bsin(kL)

Acos(kL) - Bsin(kL) = Acos(kL) + Bsin(kL)

=> -Bsin(kL) = Bsin(kL) => 2B*sin(kL) = 0。

应用 BC 2: -Aksin(-kL) + Bkcos(-kL) = -Aksin(kL) + Bkcos(kL)

Aksin(kL) + Bkcos(kL) = -Aksin(kL) + Bkcos(kL)

=> Aksin(kL) = -Aksin(kL) => 2Ak*sin(kL) = 0。

分析结果： 两个 BC 都要求 k=0 或 A=0 或 B=0 或 sin(kL)=0。

如果 sin(kL) = 0，则 kL = nπ => k = nπ/L (n = ±1, ±2, ...)。此时 A 和 B 可以是任意值。

如果 k=0 (即 λ=0)，ODE 为 f''=0, f=Ax+B, f'=A。

BC1: A(-L)+B = A(L)+B => -AL = AL => 2AL=0 => A=0 (若 L≠0)。

BC2: f'(-L)=A, f'(L)=A，自动满足。

所以当 k=0 (λ=0) 时，解为 f(x) = B (任意常数)。

总结特征值和特征函数：

λ0 = 0, 对应特征函数 Φ0(x) = A0 (常数，取 A0=1)。

λn = (nπ/L)^2 (n = 1, 2, 3, ...)。对于每个 λn，k=nπ/L，此时 A 和 B 都是任意的。这意味着对于每个 n≥1，我们有两个线性无关的特征函数：cos(nπx/L) 和 sin(nπx/L)。

结论： 周期性 SLP (对于 f''+λf=0) 的特征函数集是 {1, cos(nπx/L), sin(nπx/L) | n=1, 2, ...}。这正是标准傅里叶级数的基函数集！

右上 (Top-Right): 奇异 SLP (§17.8)

回顾 SLP ODE (展开形式): p(x)f'' + p'(x)f' + q(x)f = -λw(x)f, a ≤ x ≤ b。

奇异点 (Singular Point): 如果在区间的某个端点，例如 x=a 处，p(a) = 0，则该点称为奇异点。

奇异性的影响：

当 p(a) = 0 时，ODE 在 x=a 处的 f'' 项系数为零，方程变为 p'(a)f' + q(a)f = -λw(a)f (假设 p'(a), q(a), w(a) 存在)。这看起来像一个一阶 ODE。

标准的二阶 ODE 需要 2 个边界条件来确定唯一解（或特征函数）。

如果 ODE 在一个端点变成一阶，我们似乎只能施加 1 个边界条件。

处理方法： 为了保持 SL 理论的良好性质（如特征函数正交性、完备性），在奇异点处，我们不再施加形如 αf(a)+βf'(a)=0 的显式边界条件，而是代之以一个有界性要求 (boundedness requirement)。

要求：

"f 必须在 x 趋近 a 时保持有界 (f must be bounded as x → a)"

"f 必须在 x 趋近 b 时保持有界 (f must be bounded as x → b)" (如果 x=b 也是奇异点)

重要性： 这个有界性要求取代了在奇异点处的显式边界条件，使得 SL 理论仍然适用。

右下 (Bottom-Left): 周期性 SLP (续) - 展开

用周期性 SLP 的特征函数展开 g(x):

由于特征函数集是 {1, cos(nπx/L), sin(nπx/L)}，展开式为：

g(x) = a0 * 1 + Σ [an * cos(nπx/L) + bn * sin(nπx/L)] (n=1 to ∞)。这就是标准的傅里叶级数。

权函数 w(x)=1。

计算系数 (使用正交性):

a0 = <g|1> / <1|1> = (∫[g(x)11 dx]) / (∫[111 dx]) (从 -L 到 L) = (1/(2L)) * ∫[g(x) dx]。

an = <g|cos(nπx/L)> / <cos|cos> = (∫[g(x)cos(nπx/L)*1 dx]) / (∫[cos^2(nπx/L)*1 dx]) (从 -L 到 L) = (1/L) * ∫[g(x)cos(nπx/L) dx]。

bn = <g|sin(nπx/L)> / <sin|sin> = (∫[g(x)sin(nπx/L)*1 dx]) / (∫[sin^2(nπx/L)*1 dx]) (从 -L 到 L) = (1/L) * ∫[g(x)sin(nπx/L) dx]。

这些正是前面推导出的欧拉公式。

右下 (Bottom-Right): 奇异 SLP 的影响总结

回顾：

二阶 ODE → 需要 2 个独立解 → 需要 2 个边界条件。

一阶 ODE → 只有 1 个独立解 → 只需要 1 个边界条件。

奇异点的影响： 如果 ODE 在边界点是奇异的 (p=0)，它在该点表现得像一阶 ODE。

为了能够对二阶 ODE 施加两个边界条件（或等效条件），ODE 在边界处不应是奇异的。

如果 ODE 在边界处是奇异的，则需要用有界性条件代替显式边界条件。

Page 10

左上 (Top-Left): 示例 17.8.2 (傅里叶-贝塞尔级数)

SLP 问题：

a=0, b=L

p(x)=x, q(x)=0, w(x)=x

ODE: [x * f']' + 0*f = -λ * x * f => x f'' + f' = -λx f (公式 1)

区间: 0 ≤ x ≤ L

边界分析：

p(L) = L ≠ 0 => x=L 不是奇异点。

p(0) = 0 => x=0 是奇异点。

边界条件：

BC 1 (在非奇异点 x=L): f(L) = 0 (标准 Dirichlet 条件)。

BC 2 (在奇异点 x=0): f(0) 必须有界，|f(0)| < ∞。

解的形式：

与该 ODE 相关的函数是贝塞尔函数 (Bessel function)。具体来说，第一类零阶贝塞尔函数 J0(x) 满足 xJ0'' + J0' + xJ0 = 0，这与我们的 ODE xf''+f' + λxf = 0 形式相似。

J0(x) 的性质： 在 x=0 处有界，lim (x→0) J0(x) = 1 < ∞。满足 BC 2。

因此，尝试解的形式为 Φ(x) = J0(kx)。

应用 BC 1 (f(L)=0):

Φ(L) = J0(kL) = 0。

这要求 kL 必须是 J0 函数的一个零点 (root)。

设 zn 为 J0(x) 的第 n 个正零点 (n=1, 2, 3, ...)。

z1 ≈ 2.404826

z2 ≈ 5.520078

z3 ≈ 8.653728 ...

所以 kL = zn => k = kn = zn / L (公式 2)。

特征函数： Φn(x) = J0(kn * x) = J0(zn * x / L) (公式 3)。

特征值： 将 Φn(x) 代回 ODE (1) xΦn'' + Φn' + λn x Φn = 0。利用贝塞尔方程 xJ0''(x)+J0'(x)+xJ0(x)=0 的性质（需要变量替换 y=kx），可以得到 λn = kn^2 = (zn / L)^2 (公式 4)。

左下 (Bottom-Left): 傅里叶-贝塞尔级数 (续)

归一化坐标： 令 X = x/L，则 0 ≤ X ≤ 1。

特征函数变为 Φn(X) = J0(zn * X)。

傅里叶-贝塞尔级数展开： 任何（满足某些条件的）函数 g(x) 可以展开为：

g(x) = Σ [Cn * Φn(x)] = Σ [Cn * J0(zn * x / L)] (n=1 to ∞)。

计算系数 Cn:

Cn = <g|Φn> / <Φn|Φn>

重要： 这里的内积必须使用权函数 w(x) = x。

Cn = (∫[g(x) * J0(znx/L) * x dx]) / (∫[J0(znx/L)^2 * x dx]) (积分从 0 到 L)。

应用： 傅里叶-贝塞尔级数在求解圆柱坐标下的扩散方程等问题时非常有用。

图示： 展示了前四个特征函数 J0(z1X), J0(z2X), J0(z3X), J0(z4X) 的图像。

右上 (Top-Right): 傅里叶-贝塞尔级数 - 正交性图示

验证正交性（需要权函数 w(x)=x）：

不带权函数： ∫[Φ1(x) * Φ2(x) dx] = ∫[J0(z1x/L) * J0(z2x/L) dx] (从 0 到 L) ≠ 0。

图示了 Φ1Φ2, Φ1Φ3, Φ2*Φ3 的图像，它们的积分面积看起来不为零。

带权函数 w(x)=x (或 w(X)=X): ∫[Φn(x) * Φm(x) * x dx] (从 0 到 L) = 0 (如果 n ≠ m)。

图示了 Φ1Φ2X, Φ1Φ3X, Φ2Φ3X 的图像。这些函数乘积的积分（面积）为零。

计算 <Φn|Φn> (分母): ∫[Φn(x)^2 * x dx] = ∫[J0(zn*x/L)^2 * x dx] (从 0 到 L) ≠ 0。这个积分的值已知，等于 (L^2 / 2) * [J1(zn)]^2，其中 J1 是一阶贝塞尔函数。

再次强调： 在计算傅里叶-贝塞尔级数的系数 Cn 时，不要忘记权函数 w(x)=x。

右下 (Bottom-Right): 使用 WolframAlpha 查找贝塞尔零点和绘图

查找零点函数 (BesselJZero):

BesselJZero[0, 1]：查找 J0(x) 的第一个正零点 (z1)。

BesselJZero[0, 2]：查找 J0(x) 的第二个正零点 (z2)。

BesselJZero[0, n]：查找 J0(x) 的第 n 个正零点 (zn)。

给出了 z1, z2, z3, z4 的数值。

绘图函数 (Plot):

Plot[ BesselJ[0, BesselJZero[0,1]*X], {X,0,1}]：绘制第一个特征函数 J0(z1*X) 在 [0, 1] 上的图像。

类似地绘制 J0(z2X), J0(z3X), J0(z4*X)。

图示了这四个函数的图像。

Page 11

左上 (Top-Left): 使用 WolframAlpha 计算贝塞尔函数的内积

示例 <Φ1|Φ3> (不带权函数):

Plot[BesselJ[0, BesselJZero[0,1]*X]*BesselJ[0, BesselJZero[0,3]*X], {X,0,1}]：绘制 J0(z1X) * J0(z3X) 的图像。

integrate[BesselJ[0, BesselJZero[0,1]*X] * BesselJ[0, BesselJZero[0,3]*X], {X,0,1}]：计算积分，结果 ≠ 0 (约为 0.1168)。

示例 <Φ1|Φ3> (带权函数 w(X)=X):

Plot[BesselJ[0, BesselJZero[0,1]*X]*BesselJ[0, BesselJZero[0,3]*X]*X, {X,0,1}]：绘制 J0(z1X) * J0(z3X) * X 的图像。

integrate[BesselJ[0, BesselJZero[0,1]*X] * BesselJ[0, BesselJZero[0,3]*X] * X, {X,0,1}]：计算积分，结果 = 0。验证了正交性。

示例 <Φ3|Φ3> (计算系数分母):

Plot[BesselJ[0, BesselJZero[0,3]*X]*BesselJ[0, BesselJZero[0,3]*X]*X, {X,0,1}]：绘制 J0(z3*X)^2 * X 的图像。

integrate[BesselJ[0, BesselJZero[0,3]*X] * BesselJ[0, BesselJZero[0,3]*X] * X, {X,0,1}]：计算积分，结果 ≠ 0 (约为 0.0368)。

左下 (Bottom-Left): 傅里叶-勒让德级数 (Ex 17.8.3)

给定问题：

区间: -1 ≤ x ≤ 1

ODE: (1-x^2)f'' - 2xf' = -λf。

SLP 形式：

可以将 ODE 写成 [(1-x^2)f']' = -λ * 1 * f。

所以 p(x) = 1 - x^2, q(x) = 0, w(x) = 1。

边界分析：

p(1) = 1 - 1^2 = 0

p(-1) = 1 - (-1)^2 = 0

所以 x = ±1 都是奇异点。

边界条件 (有界性要求):

BC 1: f(-1) 必须有界。

BC 2: f(+1) 必须有界。

解： 这个 SLP 的解是勒让德多项式 (Legendre Polynomials) Pn(x)。

特征值： λn = n(n+1)，n = 0, 1, 2, ...

特征函数： Φn(x) = Pn(x)。

勒让德多项式 Pn(x):

P0(x) = 1

P1(x) = x

P2(x) = (1/2)(3x^2 - 1)

P3(x) = (1/2)(5x^3 - 3x)

...

性质：

如果 n 是偶数，Pn(x) 是偶函数 (Pn(x) = Pn(-x))。

如果 n 是奇数，Pn(x) 是奇函数 (Pn(x) = -Pn(-x))。

Pn(±1) 都有界 (具体为 Pn(1)=1, Pn(-1)=(-1)^n)。满足有界性 BCs。

正交性：

权函数 w(x)=1。

<Pm|Pn> = ∫[Pm(x) * Pn(x) * 1 dx] (从 -1 到 1)

= 0 (如果 m ≠ n)

= 2 / (2n + 1) (如果 m = n)

罗德里格斯公式 (Rodrigues' formula): Pn(x) = (1 / (2^n * n!)) * d^n/dx^n [(x^2 - 1)^n]。

右上 (Top-Right): 傅里叶-勒让德级数展开

展开式： g(x) = Σ [Cn * Pn(x)] (n=0 to ∞)。

计算系数 Cn:

Cn = <g|Pn> / <Pn|Pn>

<g|Pn> = ∫[g(x) * Pn(x) * 1 dx] (从 -1 到 1)。

<Pn|Pn> = 2 / (2n + 1)。

Cn = ( (2n + 1) / 2 ) * ∫[g(x) * Pn(x) dx] (从 -1 到 1)。

图示： 展示了 P1(x), P2(x), P3(x), P4(x) 的图像。

边界值： Pn(-1) = (-1)^n, Pn(1) = 1，都是有界的。

应用： 傅里叶-勒让德级数在求解球坐标下的物理问题（如电势、温度分布）中非常有用。

右下 (Bottom-Left): 傅里叶-勒让德级数应用示例

问题： 回顾 Ex 17.7.2，要用级数展开近似函数 f(x) = x，在区间 0 ≤ x ≤ L 上。现在尝试用勒让德级数。

步骤 1: 区间变换

勒让德多项式定义在 [-1, 1] 上。需要将 [0, L] 映射到 [-1, 1]。

使用线性变换：X = (2x / L) - 1。

反解：x = L(X + 1) / 2。

当 x=0 时，X = -1。当 x=L 时，X = +1。

步骤 2: 变换函数

需要展开的函数现在是关于 X 的函数 g(X) = f(x) = f(L(X+1)/2)。

如果 f(x) = x，那么 g(X) = L(X + 1) / 2。

步骤 3: 计算勒让德系数 Cn

Cn = ( (2n + 1) / 2 ) * ∫[g(X) * Pn(X) dX] (从 -1 到 1)。

C0 (n=0): P0(X)=1。

C0 = (1/2) * ∫[ L(X+1)/2 * 1 dX ] = (L/4) * [X^2/2 + X] (从 -1 到 1)

= (L/4) * [ (1/2 + 1) - (1/2 - 1) ] = (L/4) * [ 3/2 - (-1/2) ] = (L/4) * 2 = L/2。

C1 (n=1): P1(X)=X。

C1 = (3/2) * ∫[ L(X+1)/2 * X dX ] = (3L/4) * ∫[X^2 + X dX]

= (3L/4) * [X^3/3 + X^2/2] (从 -1 到 1)

= (3L/4) * [ (1/3 + 1/2) - (-1/3 + 1/2) ] = (3L/4) * [ 5/6 - 1/6 ] = (3L/4) * (4/6) = L/2。

Cn (n ≥ 2):

∫[g(X)Pn(X)dX] = ∫[ (L/2)(X+1) * Pn(X) dX ] = (L/2) * [ ∫[XPn(X)dX] + ∫[1Pn(X)dX] ]

∫[1*Pn(X)dX] = ∫[P0(X)Pn(X)dX] = 0 (对于 n≥1，根据正交性)。

∫[X*Pn(X)dX] = ∫[P1(X)Pn(X)dX] = 0 (对于 n≥2，根据正交性)。

因此，对于 n ≥ 2，积分项为零，Cn = 0。

展开结果：

g(X) = C0P0(X) + C1P1(X) + C2*P2(X) + ...

g(X) = (L/2)*P0(X) + (L/2)*P1(X) = (L/2)*1 + (L/2)*X

换回 x:

f(x) = g(X) = L/2 + (L/2) * [ (2x/L) - 1 ] = L/2 + x - L/2 = x。

结论： 对于 f(x)=x 这个简单的线性函数，它的勒让德级数展开（经过区间变换后）只包含前两项，并且精确地等于原函数。

这个详细的解释应该涵盖了PPT中的所有核心内容、公式推导和示例分析。希望对你理解这些概念有帮助！
