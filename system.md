

# A Quick overview of the proposed generative design system

## The problem of defining intelligence

The difficulty in even understanding how we could one day achieve general intelligence outside of humans is clearly evident in the difficulty to even define what intelligence is. In the context of AI research, Legg and Hutter {cite}`legg2007collection`  summarized no fewer than 70 definitions from the literature into a single statement: “Intelligence measures an agent’s ability to achieve goals in a wide range of environments.”

In general we find two different characterizations in definitions of intelligence: one that focuses on task-specific skills and one that is focused on adaptation across many different environments and skills. The first of these is nicely summarized by Minsky’s famous 1968 definition of AI: “AI is the science of making machines capable of performing tasks that would require intelligence if done by humans” {cite}`minsky1968`, which focuses almost entirely on skills acquired at narrow tasks normally handled by humans and has since resulted in “.. developing artificial systems that perform these tasks without featuring intelligence”. {cite}`orallo2017` The second, contrary to the task-focused approach, posits that intelligence instead “lies in the general ability to acquire new skills through learning; an ability that could be directed to a wide range of previously unknown problems”. {cite}`chollet2019measure` This describes the mind as being more flexible and with the capacity to learn new skills through experience, experimentation, learning and failure.

While both approaches have their own issues with the almost impossible task of defining and formalizing intelligence, it is quite easy to induce that the second one lends itself to the problem of design intelligence and the road towards a generative design system that is able to to adapt and perform under different design constraints, in entirely new design domains and sets of problems. Essentially, the goal of such a system would be to handle design problems and situations that it has not encountered before with relative capability and quality results. One more detail for the design of such a system comes from the two most important theories of human intelligence ({cite}`vpr2005,chc2005`) which organize human cognitive abilities in a hierarchal fashion, with the strata of general intelligence at the top, broad abilities in the middle, and specialized skills and tasks at the bottom (Figure 1).




```{figure} ./figures/chc.png
---
height: 300px
name: figure-1
align: center
---
CHC's three-stratum theory presented three levels of cognition: narrow abilities (stratum I), broad abilities (stratum II) and general abilities (stratum III). 
```

## A modular, hierarchical system

This assumption that information and intelligence follows a modular-hierarchical structure is a guiding principle for the design of the proposed system. The vision is that of a mixed-initiative interface that works along with human designer (stratum III) and on a range of different design domains and problems. Tackling these complex tasks can be made possible by a hierarchical and modular structure, where each module is a specialized and task-specific node (stratum I), and each iteration of the system is composed and (re)configured by different organizations of these modules (stratum II) in order to tackle a large diversity of complex design tasks. DI therefore is thought of as a meta-learning process taking place between the human designer and the tool as she interacts, explores, (re)combines, and (re)composes configurations of different modules specialized in specific design tasks, such as searching, learning, encoding, generating, manipulating, quantifying, and communicating designs and design performance. The mixed-initiative aspect of the system becomes crucial and acts as an evolutionary shortcut to Chollet's idea of a meta-learning algorithm which is responsible for the operation of such a system. Human intelligence, from the side of the human designer, makes the whole system work.

Another way of understanding these modules is to view them through the roles they each play in the functioning of the system and in the design process itself. This also provides a useful heuristic for naming these modules according to their function (Figure 2). The Initiator  is responsible for capturing design inputs and constraints from the human designer in an easy and intuitive way and formatting them in a way that they can be used by the other modules of the system.  The Encoder is responsible for encoding input parameters to design representations (genotypes) that the system can use to evolve, visualize and evaluate individual designs. The Generator  is responsible for creating generative programs out of encoded representations and user defined constraints. These programs will then produce a collection of alternative designs to be evaluated and explored. The Prophet is responsible for quantifying design performance for each Generator output through the use of surrogate, pretrained deep learning (DL) models. The Learner is responsible for distilling the structures that are embedded in the collection of generated designs and does that by creating latent representations (embeddings) of all Generator and Prophet outputs. This allows the Learner to examine both input and performance latent spaces. The Critic is responsible for evaluating every design along with its quantified performance and selecting interesting or well-performing designs according to criteria set by the user. The Profiler is responsible for learning  from the human designer’s preferences, especially focusing on the relationship between inputs/constraints, design space, and performance. Finally, Aesop is responsible for extracting and communicating design intelligence to the human designer about the current design task, extracted from the data produced by the system.



```{figure} ./figures/Module_contept_map.jpg
---
name: figure-2
align: center
---
Roles and modules of the proposed design generation system and the relationships between them, arrows denote data transfer.
```



The modular nature of the system can manifest in a hierarchical manner, at three different conceptual levels, with potential practical implications:

* **At the level of the module**. The modules themselves can include multiple algorithms, techniques, models, methods, and code, depending on the task. For example, the Generator module can use different generative techniques, the Critic module can use different evaluation methods, the Aesop module can use multiple visualization strategies for the user to select. Thus, each module is in itself modular in a way, a very important property for addressing a diversity of complex tasks. This can potentially allow he designer to create recipes, specific combinations of modules, methods, and representations, for specific tasks.
* **At the level of the system**. The modules can be combined in different ways to create different versions of the system that can deal more efficiently with different tasks and goals which allows for hierarchical adaptation, at the system and module level, to different problem requirements. From this perspective, the system also implies an open-endedness in its structure with the potential of new modules, specialised in additional, new tasks, added by human designers in the future.
* **At the level of design**. It is also possible to use the system at different levels of the hierarchy of design. In fact, the case studies that the research will involve are designed to reflect exactly this plasticity of application. The system will be applied to urban design, massing design, floor plan design, layout design, and finally component design. At each different level of this hierarchy, from component to layout, from floor plan to building massing and urban design, the system will potentially explore the use of different representations, generative methods, evaluation processes, and fitness functions. Finally, since performance at these different levels is highly coupled, information exchange between them with regards to performance will be explored and the  impact on solutions at individual levels evaluated. 

Apart from being the central components of the proposed system, these modules and their function also guide the required literature analysis for the proposed research. This will need to cover issues and ideas concerning design representation and encoding, generative models and techniques, representation learning, evolutionary computation, search and optimization, latent space exploration and model interpretability, preference learning, gaming AI, mixed-initiative design, UI/UX design and visualization. The research questions along with a brief review of the state-of-the-art in these fields, highlighting the important ideas and research that will be useful for the development of the system, will be detailed in the next sections.

**References:**

```{bibliography} references.bib

```

