### Prophet

The Prophet module’s role is to quantify design performance for all generated designs, that are meant to be evaluated. Prophet utilizes pretrained, surrogate deep learning (DL) models which transform what is typically a costly, simulation-based evaluation of various performance metrics into a direct evaluation that happens in real-time and requires, in most cases, only a simple visual representation of the generated geometry. It should be noted that performance, in the context of the Prophet module, strictly relates to design performance and not algorithmic performance.

Prophet is crucial to the proper functioning of the proposed generative system. The feasibility of the whole system relies upon the Prophet module, indeed the main reason that such a system has not been developed yet within the AEC domain is the inescapable cost of evaluations related with design performance. These simulations vary in run time and computational demands, ranging from a few seconds to a few days or even weeks of compute time, depending on the underlying complexity of the design and the metric evaluated. Since Prophet allows us to conduct these evaluations efficiently and in real-time the system can focus instead on generation and developing a truly expressive generative capacity. Prophet is also what transforms large-scale generative design from a primarily offline process to a potentially fully online generation.

The initial version of the system will support the following design performance evaluations:


* **Human Comfort** (HC), relating to thermal, wind, and visual aspects of comfort throughout the space.
* **Daylight Performance** (DP), relating to the distribution and availability of daylight throughout interior space and based on two yearly metrics, Daylight Autonomy (DA) and Useful Daylight Illuminance (UDI) and solar availability in exterior space based on two yearly metrics, Sunlight Hours (SH) and Solar Radiation (SR). This evaluation is climate-specific therefore location-specific surrogate models will be trained. 
* **Natural Ventilation Performance** (NVP), relating to the efficiency of wind flow and ventilation throughout the space, measured in terms of flow (m/s) or volume (m3/s).

Each evaluation has its own specific scope and use and while the user should be able to select the metrics she wants for her generative experiment, the system will take care of suggesting appropriate evaluations and performance ranges according to the type of design task at hand. 

Surrogate modeling for design performance evaluation is a potentially disruptive technology given the cost of evaluations in the AEC domain. However, there has been very little adoption in practice. The only tool utilizing pretrained models for real-time prediction currently developed with practice in mind is the Intelligent Framework for Resilient Design [^1] (InFraRed). InFraRed is able to evaluate urban designs on a variety of important, and expensive, performance metrics, including wind flow and wind comfort. This research builds on the work done with InFraRed, trying to take the next step in the evolution of large-scale generative design which involves building a process that can actually take advantage of real-time performance evaluation. 

While there is little work being done in the industry, there is a lot of research work done in surrogate modeling. Here it should be noted that InFraRed, the idea on which the Prophet module is built on, is not a traditional surrogate model since it is not being trained in real time using evaluations that are run through simulations (the standard process of surrogate modeling). That said it does serve the same function, hence it is closely related. Wortmann et al. {cite}`wortmann2015` use radial-basis function surrogate modeling optimization as a method to promote understanding rather than optimization. The method trains a model by interpolating simulation data and explores the solution space in a way that prediction error reduces, within a set budget of evaluations (simulations). Westermann and Evins {cite}`WESTERMANN2019170` conduct a comprehensive review on the application of surrogate modeling in the sustainable design domain. They find 57 studies that have been conducted and develop a comprehensive matrix of the methodologies used along with the problem the method it was applied. One interesting fact is that almost all of the surrogate modeling studies were conducted on energy simulation perhaps indicating one of the disadvantages of surrogate modeling, the requirement to run online simulations which for other metrics can take a considerable amount of time, and that requirement remains the same across different studies (no transfer learning).

The use of surrogate modeling has been very popular in QD, understandable given the large number of evaluations that QD methods require (typically in the order of 100,000).  Gaier et al. {cite}`gaier2018dataefficient` use surrogate modeling and MAP-Elites as alternative to the classic optimization algorithms on a 2-dimensional airfoil optimization problem. They develop a new illumination algorithm, Surrogated Assisted Illumination (SAIL) that leverages surrogate modeling to create the map of the design space explored. Gaie et al {cite}`Gaier2017FeatureSM` show that SAIL provides a better performing solution than MAP-Elites and they also compare the QD surrogate modeling approach to a traditional CMA-ES algorithm. It turns out that in the same amount of evaluations required required for CMA-ES to optimize one cell of the design space (that has specific feature values) SAIL finds a near-optimal solution for every cell. In the Gaming AI domain, Karavolos et al. {cite}`karavolos2018` use surrogate modeling for automated level design where they are able to investigate efficiently which level structures would result in a balanced match opening up new possibilities for mixed-initiative design.

The Prophet module is perhaps the most sensitive part of the system as it relies on external functionality (surrogate or pretrained models that conduct evaluations) for its performance. The main challenge here, especially in the AEC domain where all design tasks are real-life problems with real implications, is related to validation of prediction outputs and the ability to communicate error estimates to the user. It is crucial for the human designer to be able to trust the results of Prophet which makes the visualization of uncertainty (of prediction) a crucial part of Prophet’s functionality. This uncertainty is a requirement for a mixed-initiative system of this kind to work. Another smaller, technical challenge, is to efficiently set up an inferencing pipeline that can manage both large design spaces and predict performance in real-time with a speed that can match generation and direct evaluation.

Despite all that, Prophet opens up a completely new field for generative design, where evaluation of metrics that actually matter becomes a reality. Prophet allows for essentially parametric design at generative scales and diversity, something that completely changes the way we conduct computational design. Another important aspect is that of lifelong-learning that can happen through the module. Each session the user takes part in generates a new batch of data that can be used as training inputs for model performance improvement. This continuous training can happen at different intervals, depending on user preferences, and can also be fully automated by the system. Prophet will also provide the opportunity to human designers to supply their own simulation data in order to produce new or better pretrained models. Finally, an exciting opportunity is the ability to extract latent representations of the design space not just in the input space but also in the performance space. For this, Prophet's results will be passed on to the Learner module where models will be trained to learn latent representations of the performance space.



**References:**

```{bibliography} prophet.bib

```



[^1]:  www.infrared.city
