## GAN

同时训练G（generator）和D（discriminator）两个模型。G用于根据输入生成一个图片；D用于判断G生成的图片是生成的还是自然的。训练G的目的是让D的判断错误率最大（当然这个错误率最大是为1/2。也就是D无法判断G生成的到底是生成图片还是自然图片。因为如果超过1/2其实是反向预测了）。

### Introduction

大概就是说很多判别模型取得了成功。但是生成模型难以成功。因为过去生成模型都是基于类似于最大似然之类的。

文中把discriminator比作鉴别真伪的警察。把generator比作制作假冒产品的骗子。generator会尽力生成能够以假乱真的产品和discriminator将会尽力辨别真伪。迭代的最后的结果就是两者都具有相对于其他网络更加强大的辨别或者生成能力。

### Related Work

==文中提到目前大多数成功生成模型都是参数化的表示一个概率分布函数。并通过训练的方式使这个分布函数最大化之类的。==其中最成功的就是deep Boltzmann machine （DBM）深度玻尔兹曼机。

### Adversarial nets

这一段讲了具体是如何同时训练G和D的。总的来说如下

![image-20210826163750632](C:\Users\wanwankan\AppData\Roaming\Typora\typora-user-images\image-20210826163750632.png)



在每一个迭代中进行n次discriminator的训练。一次generator的训练。交叉的作用是防止一方过拟合。