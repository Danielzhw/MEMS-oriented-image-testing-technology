# 源码说明

## 主要目标

进行微型圆孔的自动图像识别。

## 基本处理流程

第一步，滤波降噪；

第二步，二值化处理；

第三步，边缘检测；

第四步，提取边缘，拟合圆，计算圆心和半径。

## 构建需求

* Qt framework & Qt development tools (版本在 5.9.1 及以上)
* 支持 C++14 的编译器

## 结果预览

![A.out](/cpp-qt/preview/A.out.png)

A组

![B.out](/cpp-qt/preview/B.out.png)

B组

![C.out](/cpp-qt/preview/C.out.png)

C组

## 更新日志

### 1.0.0

实现了基本处理流程中的常见算法，完成用户界面设计，通过调节参数可以实现预期目标。

### 1.0.1

* 修复了 `PTile` 方法下的参数无法正确被加载的问题。
* 在圆拟合的基础上增加了几种误差校正方法：
    + 中值误差迭代校正
    + 基于连通性的误差校正
* 界面文字翻译
* 一些技术性调整

### 1.1.0

* 新增了均值平移滤波算法。
* 现在耗时长的算法会在主面板关闭后快速中断，避免出现窗口关闭后程序仍留在后台进行运算的情况。
* 现在将鼠标放在各项处理结果的缩略图上会显示原图，在图像上用鼠标右键点击可以复制或保存。
* 移除了“导出结果”按钮。
* 现在算法执行时会在主面板右下方显示相应的进度条，同时光标指针会变为“忙”状态。
* 调整了“基于连通性的误差校正”的判据，提高了误差校正的正确率。
* 其它一些技术性调整。
