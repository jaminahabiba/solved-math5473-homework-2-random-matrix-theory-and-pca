Download Link: https://assignmentchef.com/product/solved-math5473-homework-2-random-matrix-theory-and-pca
<br>
<ol>

 <li><em>Phase transition in PCA “spike” model: </em>Consider a finite sample of <em>n </em>i.d vectors <em>x</em><sub>1</sub><em>,x</em><sub>2</sub><em>,…,x<sub>n </sub></em>drawn from the <em>p</em>-dimensional Gaussian distribution N(0<em>,σ</em><sup>2</sup><em>I<sub>p</sub></em><sub>×<em>p </em></sub>+ <em>λ</em><sub>0</sub><em>uu<sup>T </sup></em>), where <em>λ</em><sub>0</sub><em>/σ</em><sup>2 </sup>is the signal-to-noise ratio (SNR) and <em>u </em>∈ R<em><sup>p</sup></em>. In class we showed that the largest eigenvalue <em>λ </em>of the sample covariance matrix <em>S<sub>n</sub></em></li>

</ol>

pops outside the support of the Marcenko-Pastur distribution if

or equivalently, if

SNR<em>.</em>

√     √             <sup>2</sup>, that is, <em>λ</em><sub>0 </sub>can be “buried” well inside the support Marcenko(Notice that         <em>γ &lt; </em>(1 + <em>γ</em>)

Pastur distribution and still the largest eigenvalue pops outside its support). All the following questions refer to the limit <em>n </em>→ ∞ and to almost surely values:

√

<ul>

 <li>Find <em>λ </em>given SNR <em>&gt; γ</em>.</li>

 <li>Use your previous answer to explain how the SNR can be estimated from the eigenvaluesof the sample covariance matrix.</li>

 <li>Find the squared correlation between the eigenvector <em>v </em>of the sample covariance matrix (corresponding to the largest eigenvalue <em>λ</em>) and the “true” signal component <em>u</em>, as a function of the SNR, <em>p </em>and <em>n</em>. That is, find |h<em>u,v</em>i|<sup>2</sup>.</li>

 <li>Confirm your result using MATLAB, Python, or R simulations (e.g. set <em>u </em>= <em>e</em>; and choose <em>σ </em>= 1 and <em>λ</em><sub>0 </sub>in different levels. Compute the largest eigenvalue and its associated eigenvector, with a comparison to the true ones.)</li>

</ul>

1

<em>Homework 2. Random Matrix Theory and PCA                                                                                                                    </em>2

<ol start="2">

 <li><em>Exploring S</em>&amp;<em>P500 Stock Prices: </em>Take the Standard &amp; Poor’s 500 data:</li>

</ol>

<a href="https://github.com/yao-lab/yao-lab.github.io/blob/master/data/snp452-data.mat">https://github.com/yao-lab/yao-lab.github.io/blob/master/data/snp452-data.mat </a>which contains the data matrix <em>X </em>∈ R<em><sup>p</sup></em><sup>×<em>n </em></sup>of <em>n </em>= 1258 consecutive observation days and <em>p </em>= 452 daily closing stock prices, and the cell variable “stock” collects the names, codes, and the affiliated industrial sectors of the 452 stocks. Use Matlab, Python, or R for the following exploration.

<ul>

 <li>Take the logarithmic prices <em>Y </em>= log<em>X</em>;</li>

 <li>For each observation time <em>t </em>∈ {1<em>,…,</em>1257}, calculate logarithmic price jumps</li>

</ul>

∆<em>Y<sub>i,t </sub></em>= <em>Y<sub>i,t </sub></em>− <em>Y<sub>i,t</sub></em>−<sub>1</sub><em>,              i </em>∈ {1<em>,…,</em>452};

<ul>

 <li>Construct the realized covariance matrix Σ<sup>ˆ </sup>∈ R<sup>452×452 </sup>by,</li>

</ul>

1257

;

<em>τ</em>=1

<ul>

 <li>Compute the eigenvalues (and eigenvectors) of Σ and store them in a descending orderˆ by {<em>λ</em><sup>ˆ</sup><em><sub>k</sub>,k </em>= 1<em>,…,p</em>}.</li>

 <li><em>Horn’s Parallel Analysis</em>: the following procedure describes a so-called Parallel Analysis of PCA using random permutations on data. Given the matrix [∆<em>Y<sub>i,t</sub></em>], apply random permutations <em>π<sub>i </sub></em>: {1<em>,…,t</em>} → {1<em>,…,t</em>} on each of its rows: ∆<em>Y</em><sup>˜</sup><em><sub>i,π</sub></em><em><sub>i</sub></em>(<em><sub>j</sub></em><sub>) </sub>such that</li>

</ul>

<table width="419">

 <tbody>

  <tr>

   <td width="164"><sup> </sup>∆<em>Y</em><sub>1</sub><em>,</em>1 ∆<em>Y</em> 2<em>,π</em><sub>2</sub>(1)[∆<em><sup>Y</sup></em><sup>˜</sup><em><sub>π</sub></em>(<em>i</em>)<em>,t</em>] = <sup></sup><sub> </sub>∆<em>Y</em><sub>3</sub><em>,π</em><sub>3</sub>(1)<sub> </sub><em>…</em>∆<em>Y</em><em>n,π<sub>n</sub></em>(1)</td>

   <td width="72">∆<em>Y</em><sub>1</sub><em>,</em>2∆<em>Y</em>2<em>,π</em><sub>2</sub>(2)∆<em>Y</em>3<em>,π</em><sub>3</sub>(2) <em>…</em>∆<em>Y</em><em>n,π<sub>n</sub></em>(2)</td>

   <td width="72">∆<em>Y</em><sub>1</sub><em>,</em>3∆<em>Y</em>2<em>,π</em><sub>2</sub>(3)∆<em>Y</em>3<em>,π</em><sub>3</sub>(3) <em>…</em>∆<em>Y</em><em>n,π<sub>n</sub></em>(3)</td>

   <td width="30"><em>…</em><em>…</em><em>… … …</em></td>

   <td width="80">∆<em>Y</em>1<em>,t </em>∆<em>Y</em>2<em>,π</em><sub>2</sub>(<em>t</em>) ∆<em>Y</em><sub>3</sub><em>,π</em><sub>3</sub>(<em>t</em><sub>) </sub><sub></sub><em>.</em><em>… </em>∆<em>Y</em><em>n,π<sub>n</sub></em>(<em>t</em>)</td>

  </tr>

 </tbody>

</table>

Define  as the null covariance matrix. Repeat this for <em>R </em>times and compute the eigenvalues of Σ˜<em><sub>r </sub></em>for each 1 ≤ <em>r </em>≤ <em>R</em>. Evaluate the <em>p</em>-value for each estimated eigenvalue <em>λ</em><sup>ˆ</sup><em><sub>k </sub></em>by (<em>N<sub>k</sub></em>+1)<em>/</em>(<em>R</em>+1) where <em>N<sub>k </sub></em>is the counts that <em>λ</em><sup>ˆ</sup><em><sub>k </sub></em>is less than the <em>k</em>-th largest eigenvalue of Σ˜<em><sub>r </sub></em>over 1 ≤ <em>r </em>≤ <em>R</em>. Eigenvalues with small <em>p</em>-values indicate that they are less likely arising from the spectrum of a randomly permuted matrix and thus considered to be signal. Draw your own conclusion with your observations and analysis on this data. A reference is: Buja and Eyuboglu, ”Remarks on Parallel Analysis”, Multivariate Behavioral Research, 27(4): 509-540, 1992.

<ol start="3">

 <li>*<em>Finite rank perturbations of random symmetric matrices: </em>Wigner’s semi-circle law (proved by Eugene Wigner in 1951) concerns the limiting distribution of the eigenvalues of random symmetric matrices. It states, for example, that the limiting eigenvalue distribution of <em>n </em>× <em>n </em>symmetric matrices whose entries <em>w<sub>ij </sub></em>on and above the diagonal (<em>i </em>≤ <em>j</em>) are i.i.d Gaussians</li>

</ol>

) (and the entries below the diagonal are determined by symmetrization, i.e., <em>w<sub>ji </sub></em>= <em>w<sub>ij</sub></em>) is the semi-circle:

<em>,</em>

where the distribution is supported in the interval [−1<em>,</em>1].

<em>Homework 2. Random Matrix Theory and PCA                                                                                                                    </em>3

<ul>

 <li>Confirm Wigner’s semi-circle law using MATLAB, Python, or R simulations (take, e.g.,<em>n </em>= 400).</li>

 <li>Find the largest eigenvalue of a rank-1 perturbation of a Wigner matrix. That is, findthe largest eigenvalue of the matrix</li>

</ul>

<em>W </em>+ <em>λ</em><sub>0</sub><em>uu<sup>T </sup>,</em>

where <em>W </em>is an <em>n </em>× <em>n </em>random symmetric matrix as above, and <em>u </em>is some deterministic unit-norm vector. Determine the value of <em>λ</em><sub>0 </sub>for which a phase transition occurs. What is the correlation between the top eigenvector of <em>W </em>+ <em>λ</em><sub>0</sub><em>uu<sup>T </sup></em>and the vector <em>u </em>as a function of <em>λ</em><sub>0</sub>? Use techniques similar to the ones we used in class for analyzing finite rank perturbations of sample covariance matrices.

[Some Hints about homework] For Wigner Matrix), the answer is

eigenvalue is

eigenvector satisfies          (