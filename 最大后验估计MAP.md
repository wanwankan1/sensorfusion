### 最大后验估计

https://blog.csdn.net/qq_32742009/article/details/81477611

Maximum A Posteriori(MAP)

和最大似然有点像，都是要找到$\hat{\theta}=argmaxF(X;\theta)$

但区别在于后面需要最大化的函数不一样。

对于最大似然（MLE）来说
$$
F(X;\theta)=\prod_{x\in X}p(x;\theta)
$$
对于最大后验（MAP）来说
$$
F(X;\theta)=p(X|\theta)p(\theta)
$$
这是因为有贝叶斯公式
$$
p(\theta|X)=\frac{p(X|\theta)p(\theta)}{p(X)}
$$
由于$p(X)$​是独立于$\theta$的，所以只取上面部分，就能最大化$\theta$​的后验概率​​​​。

由此可见最大似然（MLE）的本质是最大化在某个$\theta$下的实验结果概率；而最大后验（MAP）的本质是最大化在已知某个$X$实验结果下最大化$\theta$​的后验概率。

