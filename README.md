      # Appendix for HF-SNN

&nbsp; &nbsp; According to Section 3, binary output of neurons in SNN have high frequency. Moreover, the convolutional operation of two signals in spatial domain corresponds to the multiplication operation in frequency domain. Thus, increasing the frequency of convolutional kernel weights can reduce the information loss in SNN. 
&nbsp; &nbsp; Given a input signal <a href="https://www.codecogs.com/eqnedit.php?latex=i(x)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?i(x)" title="i(x)" /></a>, and system function <a href="https://www.codecogs.com/eqnedit.php?latex=w(x)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?w(x)" title="w(x)" /></a>, we can get
<div align=center><a href="https://www.codecogs.com/eqnedit.php?latex=i(x)&space;\otimes&space;w(x)&space;=&space;DFT(i(x))DFT(w(x))&space;=&space;I(\mu)W(\mu)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?i(x)&space;\otimes&space;w(x)&space;=&space;DFT(i(x))DFT(w(x))&space;=&space;I(\mu)W(\mu)" title="i(x) \otimes w(x) = DFT(i(x))DFT(w(x)) = I(\mu)W(\mu)" /></a></div align=center>
where <a href="https://www.codecogs.com/eqnedit.php?latex=\otimes" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\otimes" title="\otimes" /></a> is convolutional opretion, <a href="https://www.codecogs.com/eqnedit.php?latex=DFT" target="_blank"><img src="https://latex.codecogs.com/gif.latex?DFT" title="DFT" /></a> is the discrete Fourier transform, <a href="https://www.codecogs.com/eqnedit.php?latex=x" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x" title="x" /></a> is the variable in spatial domain, <a href="https://www.codecogs.com/eqnedit.php?latex=\mu" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\mu" title="\mu" /></a> is the variable in frequency domain, <a href="https://www.codecogs.com/eqnedit.php?latex=I(\mu)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?I(\mu)" title="I(\mu)" /></a> and <a href="https://www.codecogs.com/eqnedit.php?latex=W(\mu)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?W(\mu)" title="W(\mu)" /></a> are signals in frequency domain corresponding to <a href="https://www.codecogs.com/eqnedit.php?latex=i(x)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?i(x)" title="i(x)" /></a> and <a href="https://www.codecogs.com/eqnedit.php?latex=w(x)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?w(x)" title="w(x)" /></a>, respectively. The discrete Fourier transform between <a href="https://www.codecogs.com/eqnedit.php?latex=w(x)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?w(x)" title="w(x)" /></a> and <a href="https://www.codecogs.com/eqnedit.php?latex=W(\mu)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?W(\mu)" title="W(\mu)" /></a> as follows
<div align=center><a href="https://www.codecogs.com/eqnedit.php?latex=W(\mu)&space;=&space;\sum_{n=0}^N&space;w(x)e^{-j&space;\frac{2&space;\pi}{N}&space;\mu&space;n},&space;\qquad&space;\mu&space;\in&space;[0,&space;N-1]" target="_blank"><img src="https://latex.codecogs.com/gif.latex?W(\mu)&space;=&space;\sum_{n=0}^N&space;w(x)e^{-j&space;\frac{2&space;\pi}{N}&space;\mu&space;n},&space;\qquad&space;\mu&space;\in&space;[0,&space;N-1]" title="W(\mu) = \sum_{n=0}^N w(x)e^{-j \frac{2 \pi}{N} \mu n}, \qquad \mu \in [0, N-1]" /></a></div align=center>
where <a href="https://www.codecogs.com/eqnedit.php?latex=N" target="_blank"><img src="https://latex.codecogs.com/gif.latex?N" title="N" /></a> is the number of sample, <a href="https://www.codecogs.com/eqnedit.php?latex=j" target="_blank"><img src="https://latex.codecogs.com/gif.latex?j" title="j" /></a> is the imaginary unit. For the discrete Fourier transform of signal <a href="https://www.codecogs.com/eqnedit.php?latex=w(ax)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?w(ax)" title="w(ax)" /></a>, where <a href="https://www.codecogs.com/eqnedit.php?latex=a" target="_blank"><img src="https://latex.codecogs.com/gif.latex?a" title="a" /></a> is a constant, we can get
<div align=center><a href="https://www.codecogs.com/eqnedit.php?latex=DFT(w(ax))&space;=&space;\sum\limits_{n=0}^N&space;w(ax)e^{-j&space;\frac{2&space;\pi}{N}&space;\mu&space;n}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?DFT(w(ax))&space;=&space;\sum\limits_{n=0}^N&space;w(ax)e^{-j&space;\frac{2&space;\pi}{N}&space;\mu&space;n}" title="DFT(w(ax)) = \sum\limits_{n=0}^N w(ax)e^{-j \frac{2 \pi}{N} \mu n}" /></a></div align=center>
 &nbsp; &nbsp; Let Let <a href="https://www.codecogs.com/eqnedit.php?latex=y&space;=&space;ax" target="_blank"><img src="https://latex.codecogs.com/gif.latex?y&space;=&space;ax" title="y = ax" /></a>, discrete Fonrier transform can be writen as
 <div align=center><a href="https://www.codecogs.com/eqnedit.php?latex=DFT(w(y))&space;=&space;\sum\limits_{n=0}^{\frac{N-1}{a}}&space;w(y)e^{-j&space;\frac{2&space;\pi}{N}&space;\mu&space;\frac{y}{a}}&space;=&space;\frac{1}{\left|&space;a&space;\right|}&space;\sum\limits_{n=0}^{N-1}&space;w(y)e^{-j&space;\frac{2&space;\pi}{N}&space;y&space;\frac{\mu}{a}}&space;=&space;W(\frac{\mu}{a})" target="_blank"><img src="https://latex.codecogs.com/gif.latex?DFT(w(y))&space;=&space;\sum\limits_{n=0}^{\frac{N-1}{a}}&space;w(y)e^{-j&space;\frac{2&space;\pi}{N}&space;\mu&space;\frac{y}{a}}&space;=&space;\frac{1}{\left|&space;a&space;\right|}&space;\sum\limits_{n=0}^{N-1}&space;w(y)e^{-j&space;\frac{2&space;\pi}{N}&space;y&space;\frac{\mu}{a}}&space;=&space;W(\frac{\mu}{a})" title="DFT(w(y)) = \sum\limits_{n=0}^{\frac{N-1}{a}} w(y)e^{-j \frac{2 \pi}{N} \mu \frac{y}{a}} = \frac{1}{\left| a \right|} \sum\limits_{n=0}^{N-1} w(y)e^{-j \frac{2 \pi}{N} y \frac{\mu}{a}} = W(\frac{\mu}{a})" /></a></div align=center>
 &nbsp; &nbsp; When <a href="https://www.codecogs.com/eqnedit.php?latex={\left&space;|a&space;\right&space;|}&space;\in&space;(1,\infty)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?{\left&space;|a&space;\right&space;|}&space;\in&space;(1,\infty)" title="{\left |a \right |} \in (1,\infty)" /></a>, the frequency range of signal will extend. Therefore, the value of weights shrink to a small range that would increase the frequency. We add external item in loss function to limit the value of weights as follows
<div align=center><a href="https://www.codecogs.com/eqnedit.php?latex={L_p}(x,z)&space;=&space;f(x)&space;&plus;&space;g(z)&space;&plus;&space;\frac{\rho}{2}&space;{\left&space;\|{Ax&plus;Bz-c}&space;\right&space;\|}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?{L_p}(x,z)&space;=&space;f(x)&space;&plus;&space;g(z)&space;&plus;&space;\frac{\rho}{2}&space;{\left&space;\|{Ax&plus;Bz-c}&space;\right&space;\|}" title="{L_p}(x,z) = f(x) + g(z) + \frac{\rho}{2} {\left \|{Ax+Bz-c} \right \|}" /></a></div align=center>
where <a href="https://www.codecogs.com/eqnedit.php?latex=\rho" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\rho" title="\rho" /></a> is the Lagrangian multiplier. The <a href="https://www.codecogs.com/eqnedit.php?latex=f(x)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?f(x)" title="f(x)" /></a> is condition function and the <a href="https://www.codecogs.com/eqnedit.php?latex=g(z)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?g(z)" title="g(z)" /></a> is constraint function, and the <a href="https://www.codecogs.com/eqnedit.php?latex={\left&space;\|{Ax&plus;Bz-c}&space;\right&space;\|}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?{\left&space;\|{Ax&plus;Bz-c}&space;\right&space;\|}" title="{\left \|{Ax+Bz-c} \right \|}" /></a> is constraint item.
  <div align=center><a href="https://www.codecogs.com/eqnedit.php?latex={L_\rho}(w,&space;{w_p})&space;=&space;f({w_p})&space;&plus;&space;\frac{\rho}{2}&space;\cdot&space;{\left&space;\|{w-{w_p}}&space;\right&space;\|}^2" target="_blank"><img src="https://latex.codecogs.com/gif.latex?{L_\rho}(w,&space;{w_p})&space;=&space;f({w_p})&space;&plus;&space;\frac{\rho}{2}&space;\cdot&space;{\left&space;\|{w-{w_p}}&space;\right&space;\|}^2" title="{L_\rho}(w, {w_p}) = f({w_p}) + \frac{\rho}{2} \cdot {\left \|{w-{w_p}} \right \|}^2" /></a></div align=center>
where <a href="https://www.codecogs.com/eqnedit.php?latex=f({w_p})" target="_blank"><img src="https://latex.codecogs.com/gif.latex?f({w_p})" title="f({w_p})" /></a> is the loss function and <a href="https://www.codecogs.com/eqnedit.php?latex=\frac{\rho}{2}&space;\cdot&space;{\left&space;\|&space;{w-{w_p}}&space;\right&space;\|}^2" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\frac{\rho}{2}&space;\cdot&space;{\left&space;\|&space;{w-{w_p}}&space;\right&space;\|}^2" title="\frac{\rho}{2} \cdot {\left \| {w-{w_p}} \right \|}^2" /></a> is the constraint item.
  <div align=center><a href="https://www.codecogs.com/eqnedit.php?latex=h({w_p})=\frac{\rho}{2}&space;\cdot&space;{\left&space;\|&space;{{w_p}&space;-&space;sign(w)}&space;\right&space;\|}^2$&space;&plus;&space;$\frac{1}{2}&space;{\left&space;\|&space;{{w_p}&space;-&space;w}&space;\right&space;\|}^2" target="_blank"><img src="https://latex.codecogs.com/gif.latex?h({w_p})=\frac{\rho}{2}&space;\cdot&space;{\left&space;\|&space;{{w_p}&space;-&space;sign(w)}&space;\right&space;\|}^2$&space;&plus;&space;$\frac{1}{2}&space;{\left&space;\|&space;{{w_p}&space;-&space;w}&space;\right&space;\|}^2" title="h({w_p})=\frac{\rho}{2} \cdot {\left \| {{w_p} - sign(w)} \right \|}^2$ + $\frac{1}{2} {\left \| {{w_p} - w} \right \|}^2" /></a></div align=center>
 &nbsp; &nbsp; <a href="https://www.codecogs.com/eqnedit.php?latex=\rho" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\rho" title="\rho" /></a> is the balance factor between w and sign(w), which need to be a small value as perturbation. If the value is large <a href="https://www.codecogs.com/eqnedit.php?latex=w_p" target="_blank"><img src="https://latex.codecogs.com/gif.latex?w_p" title="w_p" /></a> is convert to binary
 &nbsp; &nbsp; The derivation of this formal and the derivative in a minimum value is basically zero:
<div align=center><a href="https://www.codecogs.com/eqnedit.php?latex=\frac{\partial&space;h({w_p})}{w_p}&space;=&space;\rho&space;\cdot&space;({w_p}-sign(w))&space;&plus;&space;({w_p}-w)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\frac{\partial&space;h({w_p})}{w_p}&space;=&space;\rho&space;\cdot&space;({w_p}-sign(w))&space;&plus;&space;({w_p}-w)" title="\frac{\partial h({w_p})}{w_p} = \rho \cdot ({w_p}-sign(w)) + ({w_p}-w)" /></a></div>
 &nbsp; &nbsp; Then we can deduce as follows:
<div align=center><a href="https://www.codecogs.com/eqnedit.php?latex=\rho&space;\cdot&space;({w_p}-sign(w))&space;&plus;&space;({w_p}&space;-&space;w)&space;=&space;0" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\rho&space;\cdot&space;({w_p}-sign(w))&space;&plus;&space;({w_p}&space;-&space;w)&space;=&space;0" title="\rho \cdot ({w_p}-sign(w)) + ({w_p} - w) = 0" /></a></div>
&nbsp; &nbsp; The <a href="https://www.codecogs.com/eqnedit.php?latex=w_p" target="_blank"><img src="https://latex.codecogs.com/gif.latex?w_p" title="w_p" /></a> need to be updated as follows:
<div align=center><a href="https://www.codecogs.com/eqnedit.php?latex={w_p}&space;=&space;\frac{\rho&space;\cdot&space;sign(w)&space;&plus;&space;w}{\rho&space;&plus;&space;1}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?{w_p}&space;=&space;\frac{\rho&space;\cdot&space;sign(w)&space;&plus;&space;w}{\rho&space;&plus;&space;1}" title="{w_p} = \frac{\rho \cdot sign(w) + w}{\rho + 1}" /></a></div>
&nbsp; &nbsp; Then, according to loss function, the SNN model should be updated to reach minimum value. Due to small <a href="https://www.codecogs.com/eqnedit.php?latex=\rho" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\rho" title="\rho" /></a>, we can treat <a href="https://www.codecogs.com/eqnedit.php?latex=\frac{\partial&space;w_p}{\partial&space;w}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\frac{\partial&space;w_p}{\partial&space;w}" title="\frac{\partial w_p}{\partial w}" /></a> as 1. The derivation of this formal and the *w* value need to update as follows:
<div align=center><a href="https://www.codecogs.com/eqnedit.php?latex=w&space;=&space;w&space;-&space;\eta&space;\bigtriangledown&space;f({w_p})" target="_blank"><img src="https://latex.codecogs.com/gif.latex?w&space;=&space;w&space;-&space;\eta&space;\bigtriangledown&space;f({w_p})" title="w = w - \eta \bigtriangledown f({w_p})" /></a></div>
where <a href="https://www.codecogs.com/eqnedit.php?latex=\eta" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\eta" title="\eta" /></a> is the learning rate. Using iterative learning control algorithm update the model as follows:
<div align=center><a href="https://www.codecogs.com/eqnedit.php?latex=\left\{&space;\begin{aligned}&space;&{w_b^k}&space;=&space;\frac{\rho&space;\cdot&space;sign(w^k)&space;&plus;&space;w^k}{\rho&space;&plus;&space;1}\\&space;&{w^{k&plus;1}}&space;=&space;w^k&space;-&space;\eta&space;\bigtriangledown&space;f(w_p^k)&space;\end{aligned}&space;\right." target="_blank"><img src="https://latex.codecogs.com/gif.latex?\left\{&space;\begin{aligned}&space;&{w_b^k}&space;=&space;\frac{\rho&space;\cdot&space;sign(w^k)&space;&plus;&space;w^k}{\rho&space;&plus;&space;1}\\&space;&{w^{k&plus;1}}&space;=&space;w^k&space;-&space;\eta&space;\bigtriangledown&space;f(w_p^k)&space;\end{aligned}&space;\right." title="\left\{ \begin{aligned} &{w_b^k} = \frac{\rho \cdot sign(w^k) + w^k}{\rho + 1}\\ &{w^{k+1}} = w^k - \eta \bigtriangledown f(w_p^k) \end{aligned} \right." /></a></div>
where k is number of iterations.
  
