# 简介、线性SVM

知识点：
1. PLA+margin=SVM：支持向量机可以认为是感知机加上了对margin的要求；
2. 越大的margin相对越能容忍noise的存在，也就是鲁棒性更强；
3. SVM的最优化问题同样是引入了margin；
4. 最优化可以有二次规划QP解决；
5. 所谓支持向量就是离分割超平面足够近的点，实际上其他点对分割超平面的位置是不起作用的；
6. 对比正则化：
    - 正则化：最小化Ein，条件是WT*W<=C；
    - SVM：最小化WT*W，条件是Ein=0，more；
    - 一种理解是认为SVM是一种正则化方法，正则化的思路是加入margin来限制模型复杂度，也就是shatter的可能性减少了，因为不是每种可能都满足margin大于某个值的；
7. 从shatter角度看：fewer dichotomies -> smaller VC dim -> better generalization(Ein越接近Eout)；
