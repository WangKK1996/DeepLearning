这个小本子用来记一下最近做DL时遇到的一些有意思的东西：
# 一、Numpy神器
## 1、numpy.squeeze
它可以把任何一个含有1维的array的那一维给删掉：（1,25,3）->(25,3)
e.g.
>>> x = np.array([[[0], [1], [2]]])
>>> x.shape
(1, 3, 1)
>>> np.squeeze(x).shape
(3,)
>>> np.squeeze(x, axis=(2,)).shape
(1, 3)



 
