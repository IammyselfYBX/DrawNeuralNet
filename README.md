# Tikz论文插图绘制神经网络
## 1. 简介
本项目参考
[PlotNeuralNet](https://github.com/HarisIqbal88/PlotNeuralNet)

新增了一些功能
- [X] 支持中文
- [X] 支持2D图
- [ ] 支持更简单的Python调用
- [ ] 支持绘画RNN, Transformer等更复杂的网络

## 2. 使用方法
[演示视频](https://www.bilibili.com/video/BV1Trt2ezE6G/)

### 2.1 安装
```bash
git clone https://github.com/IammyselfYBX/DrawNeuralNet.git
cd DrawNeuralNet
```

### 2.2 绘制神经网络
```Paper```文件夹下存放了所有的模板, 你可以在这里新建一个文件夹, 并在其中新建一个.tex文件, 用于绘制你的神经网络.


```bash
cd Paper
mkdir <你的网络名>
cd <你的网络名>
nvim <你的网络名>.tex
```

### 2.3 引入模板
```latex
% 2维
\documentclass[border=15pt, multi, tikz]{standalone}
\usepackage{ctex}  % 引入ctex包以支持中文
\usepackage{import}
\subimport{../../layers/}{init}  % 确保路径正确
\usetikzlibrary{positioning}

\definecolor{nodecolor}{rgb}{1, 0.7, 0.5}  % 浅黄色
\definecolor{linecolor}{rgb}{0.8, 0.1, 0.1}  % 深红色
\definecolor{somelinecolor}{rgb}{0.8, 0.2, 0.2}  % 特殊的红色调用于标记特定连线

% 3维
\documentclass[border=15pt, multi, tikz]{standalone}
\usepackage{import}
\subimport{../../layers/}{init}
\usetikzlibrary{positioning}
\usetikzlibrary{3d} %for including external image 

\def\ConvColor{rgb:yellow,5;red,2.5;white,5}
\def\ConvReluColor{rgb:yellow,5;red,5;white,5}
\def\PoolColor{rgb:red,1;black,0.3}
\def\DcnvColor{rgb:blue,5;green,2.5;white,5}
\def\SoftmaxColor{rgb:magenta,5;black,7}
\def\SumColor{rgb:blue,5;green,15}
```

### 2.4 编译
```bash
latexmk -f <你的网络名>.tex
```
