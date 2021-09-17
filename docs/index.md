# SAM

<img src="img/logo.png" width="120" align="right"/>

SAM is an extensible and modular framework for simulating and studying effects of various questionable research practices, QRPs, on scientific results. It provides interfaces and APIs for designing, and experimenting on several statistical models under the influence of various *p*-hacking strategies as well as other types of QRPs. For instance, the user is able to design a simulation to could design a two-by-two factorial experiment and study the effect of optional stopping on achieving significant results. SAM offers analysis of a number of conventional and recognized *p*-hacking methods out of the box; additionally, the user will be able to implement new methods based on her preferences.

In this vignette, we will describe the underlying design principles and main features of SAM alongside some examples. In the [Design](design.md) section, we describe types of problems that SAM analyses. After setting the ground rules, we describes different components of SAM and the process of designing your own simulation.

- - - 

!!! note
	The contents of this documentation might be slightly differ from the information published by Abdol et al., 2021[@Abdol_2021]. For general introduction to SAM, please refer to the main publication while we sync the two sources.

- - - 

> The preparation of this project and its related material was supported by an ERC consolidator grant IMPROVE (grant no. 603726361) from the European Research Council.

<picture>
  <source 
      srcset="img/LOGO_ERC-FLAG_EU_Dark.jpg" 
      media="(prefers-color-scheme: dark)">
  <img src="img/LOGO_ERC-FLAG_EU_Light.jpg"/>
</picture>


\bibliography
