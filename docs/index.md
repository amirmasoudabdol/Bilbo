# SAM

SAM is an extensible and modular framework for simulating and studying effects of various questionable research practices on scientific results. It provides different interfaces and APIs for designing, and experimenting on several statistical models under the influence of various *p*-hacking strategies as well as other types of *questionable research practices*, QRPs. For instance, one could design a two-by-two factorial experiment and study the effect of optional stopping on achieving significant results. SAM offers number of conventional and recognized *p*-hacking methods out of the box; additionally, a user will be able to implement new methods based on her preferences.

In this vignette, we will describe underlying design principles and main features of SAM alongside some examples. In the [Introduction](introduction.md) section, we describe types of problems that SAM is trying to solve. After setting the ground rules, we can dive into different components of SAM and the process of designing your own simulation.

![](/figures/effin-scream-to-the-void.png)