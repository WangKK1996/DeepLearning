这个小本子用来记一下最近做DL时遇到的一些有意思的东西：
# 一、Numpy神器
## 1、numpy.squeeze
它可以把任何一个含有1维的array的那一维给删掉：（1,25,3）->(25,3)
e.g.
> x = np.array([[[0], [1], [2]]])

> x.shape

(1, 3, 1)

>np.squeeze(x).shape

(3,)

> np.squeeze(x, axis=(2,)).shape

(1, 3)

## 2、numpy.reshape
参数设置：np.reshape(a, newshape, order='C').

其中有一个newshape参数，可以选为-1，代表根据前面给出的数据，然后“推断出（infer）”剩下的维度。

刚刚在把一个（209,96,96,3）的数组转船成（209,96*96*3）的array时就用到了这个函数：
> a.reshape(a.shape[0], -1)

## 3、np.dot()
和直观感受不一样，np.dot实际上对于矩阵做的是矩阵乘法（而不是点乘）

# 一些小tips
1、计算正确率：
Plot the decision boundary for logistic regression

> plot_decision_boundary(lambda x: clf.predict(x), X, Y)

> plt.title("Logistic Regression")

Print accuracy

> LR_predictions = clf.predict(X.T)

> print ('Accuracy of logistic regression: %d ' % float((np.dot(Y,LR_predictions) + np.dot(1-Y,1-LR_predictions))/float(Y.size)*100) +'% ' + "(percentage of correctly labelled datapoints)")

重点在于这个**np.dot(Y,LR_predictions) + np.dot(1-Y,1-LR_predictions)**,学习了学习了。

 
