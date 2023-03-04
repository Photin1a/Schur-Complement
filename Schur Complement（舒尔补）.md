# Schur Complement（舒尔补）

[SLAM基础——舒尔补介绍](https://blog.csdn.net/jdy_lyy/article/details/119258928)

## 1、定义

定义$M=\begin{bmatrix}A&B\\C&D\end{bmatrix}$，若$A$可逆，则$\Delta A=D-CA^{-1}B$称为$A$关于$M$的舒尔补；

                                      若$D$可逆，则$\Delta D=A-BD^{-1}C$称为$D$关于$M$的舒尔补。

## 2、性质

$$
M=\begin{bmatrix}A&B\\C&D\end{bmatrix}=\begin{bmatrix}I&0\\CA^{-1}&I\end{bmatrix}\begin{bmatrix}A&0\\0&\Delta      A\end{bmatrix}\begin{bmatrix}I&A^{-1}B\\0&I\end{bmatrix}\\ M^{-1}=\begin{bmatrix}A&B\\C&D\end{bmatrix}^{-1}=\begin{bmatrix}I&-A^{-1}B\\0&I\end{bmatrix}\begin{bmatrix}A^{-1}&0\\0&\Delta      A^{-1}\end{bmatrix}\begin{bmatrix}I&0\\-CA^{-1}&I\end{bmatrix}\\=\begin{bmatrix}A^{-1}+A^{-1}B\Delta A^{-1}CA^{-1}&-A^{-1}B\Delta A^{-1}\\-\Delta A^{-1}CA^{-1}&\Delta A^{-1}\end{bmatrix}
$$

$$
M=\begin{bmatrix}A&B\\C&D\end{bmatrix}=\begin{bmatrix}I&BD^{-1}\\0&I\end{bmatrix}\begin{bmatrix}\Delta D&0\\0&D\end{bmatrix}\begin{bmatrix}I&0\\D^{-1}C&I\end{bmatrix}\\ M^{-1}=\begin{bmatrix}A&B\\C&D\end{bmatrix}^{-1}=\begin{bmatrix}I&0\\-D^{-1}C&I\end{bmatrix}\begin{bmatrix}\Delta D^{-1}&0\\0&D^{-1}\end{bmatrix}\begin{bmatrix}I&-BD^{-1}\\0&I\end{bmatrix}\\=\begin{bmatrix}\Delta D^{-1}&-\Delta D^{-1}BD^{-1}\\-D^{-1}C\Delta D^{-1}&D^{-1}+D^{-1}C\Delta D^{-1}BD^{-1}\end{bmatrix}
$$

> $\Delta A=D-CA^{-1}B$,    $\Delta D=A-BD^{-1}C$
> 

## 3、应用

### （1）解方程组

$$
\begin{bmatrix}A&B\\C&D\end{bmatrix}\begin{bmatrix}x_1\\x_2\end{bmatrix}=\begin{bmatrix}b_1\\b_2\end{bmatrix}
$$

法1：$D^{-1},\Delta D^{-1}$存在

$$
\begin{bmatrix}x_1\\x_2\end{bmatrix}=\begin{bmatrix}\Delta D^{-1}(b_1-BD^{-1}b_2)\\D^{-1}(b_2-Cx_1)\end{bmatrix}
$$

法2：$A^{-1},\Delta A^{-1}$存在

$$
\begin{bmatrix}x_1\\x_2\end{bmatrix}=\begin{bmatrix}A^{-1}(b_1-Bx_2)\\\Delta A^{-1}(b_2-CA^{-1}b_1)\end{bmatrix}
$$

### （2）联合概率分解

![Untitled](Schur%20Complement%EF%BC%88%E8%88%92%E5%B0%94%E8%A1%A5%EF%BC%89%20f4fb1fe6f9c44bdb887413be31bc429e/Untitled.png)