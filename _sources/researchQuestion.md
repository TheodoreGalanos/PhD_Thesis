















### Aesop

Role (from paper):

If the Critic was the heart, or engine, of the system, then following the same metaphor the Aesop is the brain. Aesop's main function is to extract and communicate design intelligence to the human designer. While this includes visualizations of geometry and performance outputs, latent space exploration, and statistical analysis, it is not simply a process of visualization but rather one of exploration.  

Another important role of Aesop is latent space exploration and visualization based on the learned embeddings the learner module produces.

Following the idea of intelligence emerging as an interaction between the designer and a modular system, the aesop should provide a \hl{declarative,} modular visual exploration environment in an interface where the human designer can quickly and intuitively construct her own visualizations through simple drag and drop operations. This allows for a type of polymorphism, different views based on user needs and data types. %The interface will use vega-lite, an open-source, high-level grammar for visual analysis that generates interactive visualizations. 
Another important role of Aesop is latent space exploration and visualization based on the learned embeddings the learner module produces. Aesop should allow for multiple ways to explore the latent space: dimensionality reduction in order to visualize high-dimensional data in a human-readable way, clustering plots that aim to extract some structure within the designs generated, and latent space interpolation that takes advantage of the latent space to traverse from one design to the other, based on user selected criteria. Interpolation is one of the most fascinating aspects of the Aesop since it could enable a novel way of viewing and understanding results by taking ``targeted walks'' through the design space by selecting a pair of candidate seed designs and the number of interpolation steps between them.

Literature review (TODO) on Aesop:

Challenges:

While the ultimate goal of Aesop is to extract and communicate design intelligence, the biggest challenge is that there really hasn't been any practical or theoretical work on what constitutes design intelligence, in relation to design space exploration. It is very much an open question and one that will need to be answered in practice. Another challenge is balancing between custom and template visualizations. The interface needs to be both intuitive and provide easy access to most of the views discussed above without sacrificing the capacity of the user to explore her data. On the other end of the spectrum, since the goal of the system is to be helpful in practice, it eventually needs to produce detailed reports that provide useful insights concerning the generation process and its outcomes, including details concerning regulatory compliance, costs, and performance. A final challenge is to enable the multiple view architecture, providing different data views based on either type of user or data in question, which is a difficult engineering problem.

Opportunities:

The biggest opportunity in the Aesop module is also one of the main goals of the system: to generate, extract, and articulate design intelligence. An interface like the one described would provide new ways to navigate design spaces and construct visualizations that are not only intuitive and informative but also could help us discover novel insights and build a new intuition of design performance. For this reason, the tools can be also thought of as a high-order learning tool, not simply making the process faster and easier, although it could also do that, but also a much fuller experience in which the human designer interacts and co-creates its design vision.

Instances in Architecture:



### Bibliography



```{bibliography} researchQ.bib

```

 







