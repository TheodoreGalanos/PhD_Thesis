# Critic

The role of the Critic is to evaluate all generated designs coming out of the generator, according to constraints communicated by the Initiator, fitness calculated from evaluations of the Prophet, latent representations provided by the Learner, and its own direct evaluations of designs. From this short description it is obvious that the Critic module is the heart of the system, bringing together almost all previous modules in the process of evaluation and search through the design space. The Critic also checks designs for validity based on both user constraints and geometric constraints related to the architectural domain (e.g. layouts must be closed or buildings can not intersect). There is a range of evaluations that happen within the critic that involve different aspects, qualities and quantities of design performance, a detailed description can be seen in the Table below.



| Details on evaluation tasks performed by the Critic module |                                                              |
| ---------------------------------------------------------: | :----------------------------------------------------------- |
|                                   **Daylight Performance** |                                                              |
|                                                Description | measures the distribution and availability of daylight in indoor spaces |
|                                           Possible Metrics | spatial daylight autonomy (SDA) {cite}`nabil_useful_2005`, useful daylight illuminance (UDI), melanomic lux (EML) {cite}`danell_evaluating_nodate`, non-visual Direct-Response (nvRD) {cite}`danell_evaluating_nodate` |
|                                              Output Format | grid-based, array                                            |
|                                    Computational Intensity | high                                                         |
|                                        Calculation details | Prophet, online                                              |
|                                 **Visibility Performance** |                                                              |
|                                                Description | measures the quantity and quality of views to the outside world from every location of the analysis grid |
|                                           Possible Metrics | space syntax {cite}`hillier_hanson_1984` approaches including visibility graph analysis (VGA), visual connectivity and visual integration [cite}`turner2011vga` and augmented VGA {cite}`Varoudis2015VisibilityAA` analysis |
|                                              Output Format | graph-based and grid-based, array format                     |
|                                    Computational Intensity | low                                                          |
|                                        Calculation details | Critic, online                                               |
|                            **Thermal Comfort Performance** |                                                              |
|                                                Description | measures occupants' comfort throughout the year              |
|                                           Possible Metrics | Predicted Mean Vote (PMV) {cite}`fanger_thermal_1970`, Physiological Equivalent Temperature (PET) {cite}`hoppe_heat_1993`, Universal Thermal Climate Index {cite}`utci` |
|                                              Output Format | grid-based, array format                                     |
|                                    Computational Intensity | very high                                                    |
|                                        Calculation details | Prophet, online                                              |
|                        **Natural Ventilation Performance** |                                                              |
|                                                Description | measures the availability and magnitute of wind flow and (non mechanical) ventilation through the space |
|                                           Possible Metrics | m/s, m3/s                                                    |
|                                              Output Format | grid-based, array format and space-based (average, min, max) |
|                                    Computational Intensity | very high                                                    |
|                                        Calculation details | Prophet, online                                              |
|                              **Network-based Performance** |                                                              |
|                                                Description | measures the effect of layout design on aspects related to flow, occupancy, accessibility, and efficiency of traversing the space |
|                                           Possible Metrics | adjacencies, connectivity, buzz {cite}`nagy_buzz_2017`, distraction, space for communication {cite}`pachilova_providing_2020` |
|                                              Output Format | graph-based and grid-based, array format                     |
|                                    Computational Intensity | low                                                          |
|                                        Calculation details | Critic, online                                               |
|                                   **Acoustic Performance** |                                                              |
|                                                Description | measures noise levels and noise dissipation given interior or exterior sources of sound |
|                                           Possible Metrics | dBA                                                          |
|                                              Output Format | grid-based, array format                                     |
|                                    Computational Intensity | medium                                                       |
|                                        Calculation details | Prophet, online                                              |
|                                     **Safety Performance** |                                                              |
|                                                Description | measures the impact of layout design to egress time          |
|                                           Possible Metrics | distance-to-exit                                             |
|                                              Output Format | grid-based, array format                                     |
|                                    Computational Intensity | low                                                          |
|                                        Calculation details | Critic, online                                               |
|                                **Crowd-based Performance** |                                                              |
|                                                Description | measure impact of design to behavioral responses of occupants |
|                                           Possible Metrics | evacuation time, exit flow rate, traveled distance           |
|                                              Output Format | grid-based, array format                                     |
|                                    Computational Intensity | high                                                         |
|                                        Calculation details | Critic, offline                                              |
|                                      **Model Performance** |                                                              |
|                                                Description | measure geometric properties of generated designs            |
|                                           Possible Metrics | area (m2), number of rooms, number of different spaces, material quantities, window to wall ratio, cost, environmental emissions |
|                                              Output Format | value-based, array format                                    |
|                                    Computational Intensity | low                                                          |
|                                        Calculation details | Critic, online                                               |
|                                                            |                                                              |



Literature review (TODO) on Critic:



Challenges:

The main challenge for the critic module is to develop flexible processes for assessing constraints of different types, used in the various evaluations the user has selected, across different use cases and design tasks. This includes an efficient way to incorporate information from different sources such us initiator and encoder, prophet, and generator. A more conceptual problem related to the high-dimensional nature of architectural design spaces is how to restrict the search without compromising novelty in generated designs.

Opportunities:

The most exciting opportunity is being able to evaluate designs in the latent space instead of or in combination with the output space. This can provide a much more intuitive way for human designers to guide generation and understand the relationship between their design decisions and the outputs the system produces. Another opportunity is to create a tool that can evaluate functions related to the use and operation of the buildings, apart from the traditional design performance approach. Finally, another opportunity is to explore the co-evolution between design performance and morphology within perhaps a reinforcement learning (RL) framework.



```{bibliography} critic.bib

```