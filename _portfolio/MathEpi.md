---
title: Mathematical Epidemiology 
excerpt: "Short description of portfolio item number 1<br/><img src='/images/500x300.png'>"
collection: portfolio
author: Mason A. McCallum
---


<div>
	<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
	<script type="text/javascript" id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js">
	</script>
</div>

I will start with a simple disease model to introduce some key terms.

<div>
\begin{align*}
	&S'(t)=\Lambda-\beta I S-\mu S\\
	&I'(t)=\beta I S-\alpha I-\mu I\\
	&R'(t)=\alpha I-\mu R\\
	& \\
	&N'(t)=\Lambda-\mu N\\
	&N(t)=S+I+R\\
\end{align*}
</div>
	
The non-dimensionalization of this system becomes the following:

<div>
	\begin{align*}
		&x'=\rho(1-x)-\mathscr{R}_0xy\\
		&y'=(\mathscr{R}_0x-1)y\\
		&\rho=\frac{\mu}{\alpha+\mu}\\
		&\mathscr{R}_0=\frac{\Lambda\beta}{\mu(\alpha+\mu)}\\
	\end{align*}

	\begin{equation*}
		J(x,y)=\left(
		\begin{array}{cc}
		 -\rho -\mathscr{R}_0 y & -\mathscr{R}_0 x \\
		 \mathscr{R}_0 y & \mathscr{R}_0 x-1 \\
		\end{array}
		\right)
	\end{equation*}
		This system has two equilibrium, the disease free equilibrium and the endimic equilbrium.
	\begin{align*}
		&\mathscr{E}_0=(1,0)\\
		&\mathscr{E}_1=(\frac{1}{\mathscr{R}_0},\frac{(\mathscr{R}_0-1)\rho}{\mathscr{R}_0})\\
	\end{align*}
</div>
	
To better understand the behavior of this system lets look at stability conditions on the DFE.
<div>
	\begin{align*}
	&J(\mathscr{E}_0)=\left(
	\begin{array}{cc}
	 -\rho  & -R \\
	 0 & R-1 \\
	\end{array}
	\right)\\
	&\lambda_1=-\rho\\
	&\lambda_2=\mathscr{R}_0-1\\
	\end{align*}
	We have a stable DFE if \(\mathscr{R}_0<1\) and a saddle otherwise.
	\begin{align*}
	&J(\mathscr{E}_1)=\left(
	\begin{array}{cc}
	 -\rho -(\rho  (R-1)) & -1 \\
	 \rho  (R-1) & 0 \\
	\end{array}
	\right)\\
				&|J(\mathscr{E}_1)-\lambda I|=\lambda^2+\rho\mathscr{R}_0\lambda+\rho(\mathscr{R}_0-1)=0\\
				&\lambda_{1,2}=\frac{-\rho\mathscr{R}_0\pm\sqrt{(\rho\mathscr{R}_0)^2-4(\mathscr{R}_0\rho-\rho)}}{2}\\
	\end{align*}
</div>
	
<iframe src="https://www.desmos.com/calculator/7jigvs9stp" style="min-height:300px" width="100%"></iframe> 

# What is $$\mathscr{R}_0$$?
From the system above we had a term $$\mathscr{R}_{0}=\frac{\beta\Lambda}{\mu(\alpha+\mu)}$$. This is known as the reproduction number of the disease. This term is one you commonly see on the media because it is a key estimate of contagiousness that is a function of human behavior and biological characteristics of pathogens[1]. This is defined as the number of secondary infections that one infective host may produce in a population of susceptible host individuals. I need to introduce a term often used in chemistry known as the law of mass action. In epidimiology this means that the rate of disease transmission if proportional to the product of the number of individuals. In the system above you can see that $$\beta I S$$ is the mass action term in our equation. Now Notice that from the system $$\alpha+\mu$$ is the rate that individuals leave the infective class. Therefore $$\frac{1}{\alpha+\mu}$$ is the average time an individual spends in the infective class. Now condiser the case where we have one individual and the rest are suseptible individuals. Our Law of mass action states that 
$$\frac{\beta\Lambda}{\mu}$$ is the number of infections one individual makes per unit time. Therefore we get that the number of transmissions one infected individual can make in a totally suseptible population is: $$\mathscr{R}_0=\frac{\beta\Lambda}{\mu(\alpha+\mu)}$$
<br>
<br>
We have some conditions on what we can call an $$\mathscr{R}_0$$.
<ul>
	<li>Be nonnegative for nonnegative parameter values</li>
	<li>Be zero if there is no transmission</li>
	<li>Be interpretable as the number of secondary infections.</li>
</ul>

$$\mathscr{R}_0$$ is the threshold condition for the stability of the disease-free equilibrium. The goal is to identify a dimensionless expression. If we impose stability conditions at our DFE on the 2x2 jacobian we will obtain the $$\mathscr{R}_0$$. With more complex systems we will need other methods to identify this threashold condition this however will come at a cost. The $$\mathscr{R}_0$$ found using more complex methods are often harder to interpret as the number of secondary infections.  

# Lotka-Voltera Model with SI Disease in Prey
<div>
	\begin{align*}
	&S'(t)=rS(1-\frac{N}{K})-\gamma_s SP-\beta SI\\
	&I'(t)=\beta SI-\gamma_I IP-\mu_0 I\\
	&P'(t)=\epsilon(\gamma_s S+\gamma_I I)P-dP\\
	\end{align*}
</div>

 $$\gamma_s$$ and $$\gamma_x$$ are the predation rates of susceptable and infected prey, $$\beta$$ is the transmission rate of the disease in the prey, and $$\mu_0$$ is the natural or disease-induced death rate of infected prey.<br><br>

The Lotka-Voltera model makes a few necessary assumptions.
<ul>
	<li>The Prey population finds ample food at all times.</li>
	<li>The food supply of the predator population depends entierly on the prey population</li>
	<li>The rate of change of population is proportional to its size.</li>
	<li>During the process, the environment does not change in fovor of one species, and genetic adaptation is sufficiently slow.</li>
</ul>
When we add is the SI Disease we add the following assumptions.
<ul>
	<li>The disease is transmitted only in the prey.</li>
	<li>Infected prey do not recover from the disease.</li>
	<li>Attack rates of the predator for healthy and infected prey may be different.</li>
	<li>Infected prey does not reporoduce but participates in the competition for resources, so it participates in self-limitation.</li>
</ul>
	
<div>
		$$
		J(S,I,P)= \left(
			\begin{array}{ccc}
				r \left(1-\frac{S+I}{K}\right)-\frac{r S}{K}-P \gamma _s-\beta  I & -\frac{r
				S}{K}-\beta  S & -S \gamma _s \\
				\beta  I & -\mu _0-P \gamma _I+\beta  S & -I \gamma _I \\
				P \epsilon  \gamma _s & P \epsilon  \gamma _I & \epsilon  \left(S \gamma _s+I
				\gamma _I\right)-d \\
			\end{array}
		\right)
		$$
</div>
	
When we solve this system for equilibrium we find 6 such points quickly using Mathematica. However we notice that one of those has strictly negative predator population and is therefore excluded from our analysis.

<iframe width='800' height='400' src='https://www.wolframcloud.com/obj/186ddde1-9767-48f1-b4da-d46d3d76f6d6' frameborder='0'></iframe>

#### Extinction equilibrium
<div>	
	\begin{align*}
	&\mathscr{E}_0=(0,0,0)\\
	\end{align*}
</div>
	
#### predator extinction endemic equilibrium
<div>
	\begin{align*}
	&\mathscr{E}_1=(\frac{\mu _0}{\beta },\frac{r \left(\beta K-\mu _0\right)}{\beta (\beta K+r)},0)\\
	\end{align*}
</div>
	
#### Disease-free and predator free equilibrium
$$
\begin{align*}
&\mathscr{E}_2=[K,0,0]\\
\end{align*}
$$
	
#### Disease Free Equilibrium (DFE)
$$
\begin{align*}
&\mathscr{E}_3=(\frac{d}{\epsilon \gamma_s},0,\frac{r \gamma_s^{2} \left(K \epsilon \gamma_s-d\right)}{K \epsilon })\\
\end{align*}
$$
	
#### Coexistence equilibrium
$$
\begin{align*}
&\mathscr{E}_4=(\frac{\beta d K+d r-K r \epsilon \gamma_I-K \mu _0 \epsilon \gamma_s}{r \epsilon \gamma_s-r \epsilon \gamma_I},-\frac{\beta d K \gamma_s+d r \gamma_I-K r \epsilon \gamma_s \gamma_I-K \mu _0 \epsilon \gamma_2^s}{r \epsilon \gamma_s \gamma_I-r \epsilon \gamma_2^I},\frac{r \epsilon \gamma_I \left(\beta K-\mu _0\right)-(\beta K+r) \left(\beta d-\mu _0 \epsilon \gamma_s\right)}{r \epsilon \gamma _I \left(\gamma_I-\gamma _s\right)})\\
\end{align*}
$$


## World Mosquito Program
Lastly, I want to conclude with a current project that is underway to reduce Mosquito-borne illness in areas like Africa and Southeast Asia. Scientists introduce bacteria to a population of Male mosquitos which then breed. These and the offspring, given the vertical transmission of Wolbachia, are no longer viable vectors for diseases like Dengue and malaria. There are many exciting insights that mathematicians bring to the table in order to drive this effort to stabilize the disease-free equilibrium. Even cooler though is we are fighting a vector-borne illness with Mosquitos.
## Conclusion
I hope that some of my interest and excitement in this subject has found its way to you. I find that the nonlinearity and complexity of these models lend themselves to some interesting mathematics all the while providing an opportunity to make an impact on the world. The scope of my project shifted a little as I faced challenges analyzing the LV.SI model however I hope you enjoyed it. Going forward with these studies I am interested in developing and reading about more complex disease models. In particular, I am interested studying epi with more realistic human movement models.
## References
Maia Martcheva's: <a href="https://link.springer.com/book/10.1007/978-1-4899-7612-3">"Intro to Mathematical Epidemiology"</a><br>
World Mosquito Program: <a href="https://www.worldmosquitoprogram.org/">Wolbachia program</a><br>
CDC: <a href="https://www.cdc.gov/globalhealth/ntd/diseases/index.html">Neglected Tropical Diseases</a><br>
