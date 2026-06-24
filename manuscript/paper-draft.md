\# Abstract



The Stroop task is a classic paradigm for studying cognitive interference, selective attention, and response competition. By analyzing behavioral data from 81 participants, this study examined how congruent, incongruent, and neutral conditions affect reaction time and accuracy. The dataset contained trial-level responses from a publicly available Stroop experiment. In the preprocess, probe trials, invalid reaction times, and extreme values were removed. In addition, the participant–session structure in the raw files was resolved. The results showed a robust Stroop interference effect. The fastest reaction times were in the congruent condition, and the slowest in the incongruent condition. The neutral condition contained intermediate performances. The mean interference effect is defined as the difference in reaction time between incongruent and congruent trials. It was 106 ms. A paired-samples t-test confirmed a significant difference between incongruent and congruent conditions, with t(80) = 17.77, p < .001, and a large effect size (dz = 1.97). It showed strong interference at the group level. Accuracy remained high across conditions, with little evidence of a speed–accuracy trade-off. Assumption checks supported the use of parametric analysis.



\# Introduction



The Stroop task is one of the widely used paradigms for studying cognitive interference, selective attention, and cognitive control. In the classic color-word version of the Stroop task, participants are required to identify the ink color of a stimulus while ignoring its semantic content.  When the word meaning conflicts with the ink color, for instance, the word ‘RED’ printed in blue ink, performance is generally slower and less accurate than when the meaning and the color are consistent. This phenomenon is known as the Stroop effect. It was first systematically documented by Stroop (1935) and thereafter became a central tool for studying how competing sources of information influence behavior. Decades of research have indicated that the Stroop effect is robust across a wide range of experimental settings and populations. Indeed, it became one of the most reliable findings in cognitive psychology (MacLeod, 1991). The Stroop task, in both experimental and applied contexts, remains a standard measure of cognitive interference and inhibitory control (Scarpina \& Tagini, 2017).



Although the behavioral pattern itself is well established, its underlying cognitive cause remains the subject of theoretical debate. Early accounts emphasized automaticity, suggesting that reading is a highly practiced process, and it is difficult to suppress when participants are instructed to name ink colors. Other approaches have focused on selective attention and the allocation of processing resources to task-relevant information. More recent theories emphasize response conflict and cognitive control mechanisms. In conflict-monitoring frameworks, interference arises because competing representations activate incompatible responses; as a result, for control processes that regulate behavior, it increases the demand (Botvinick et al., 2001). At the same time, contemporary reviews argue that Stroop interference cannot be attributed to a single processing stage and may reflect contributions from perceptual, semantic, and response-level sources of conflict. Consequently, important questions remain about the exact origins of the effect and the interpretation of behavioral measures that are caused by Stroop performance (Parris et al., 2022).



Building on this literature, the present study adopts a data-driven and reproducible analytical approach rather than attempting to adjudicate between competing theoretical accounts. Using an openly available trial-level dataset, the study quantifies Stroop interference across congruent, incongruent, and neutral conditions, examines inter-individual variability in interference magnitude, and evaluates whether a simple additive baseline-plus-interference model can account for observed behavioral patterns. In addition to group-level estimates of reaction time and accuracy effects, the analysis characterizes variability across participants, providing a more fine-grained description of performance than condition averages alone.



The primary aim of the study is to examine the impact of cognitive interference on reaction time and accuracy in the Stroop task. It is hypothesized that incongruent trials will produce slower responses than congruent trials, with neutral trials yielding intermediate performance. A secondary aim is to quantify individual differences in interference magnitude. Finally, a simple computational model is used to evaluate whether an additive structure can reproduce the main behavioral effects observed in the empirical data. Together, these analyses provide a transparent and reproducible characterization of Stroop performance while illustrating how behavioral analysis and computational modeling can be integrated within a unified framework.



\# Methods

&nbsp;	

\## Participants

&nbsp;	

The dataset consisted of 85 subject-session files corresponding to 81 unique participants. Inspection of file identifiers revealed a hierarchical structure in which some participants contributed multiple recording sessions. To resolve this, participant identity and session identity were explicitly separated, yielding a subject–session–trial data structure. All analyses in this manuscript were conducted at the participant level by aggregating trials across sessions within each participant. Sessions were not treated as independent statistical units, and no participant was excluded on the basis of having multiple sessions. This aggregation ensured that inferential statistics respected the independence assumption at the participant level while retaining all available trial-level observations.



\## Dataset



The dataset comprised trial-level behavioral responses from a computerized Stroop task. It included reaction time (RT) and accuracy measures across experimental conditions. The dataset is linked to an OSF project (https://osf.io/kxpqu/overview) and contains structured experimental recordings of cognitive interference under congruent, incongruent, and neutral stimulus conditions.



\## Design

&nbsp;	

The study used a within-subject Stroop design with repeated measures. Each participant completed trials in congruent, incongruent, and neutral conditions. The main experimental manipulation was the interference between stimulus meaning and response requirements, measured through these conditions.



\## Variables



Reaction time (RT) was defined as the interval between stimulus presentation and participant response. Accuracy was coded as a correct or incorrect response on each trial. Condition was categorized into three levels: congruent, neutral, and incongruent. Participant ID defined unique subject identifiers after resolving the file-based session structure. The Stroop effect was computed at the participant level as the mean RT difference between the incongruent and congruent conditions.



\## Preprocessing



Raw data underwent several preprocessing steps before analysis. First, probe trials were removed from the dataset. Second, reaction time values below 200 ms and above 2000 ms were excluded as unusually fast or delayed responses. Third, RT values coded as -1 were treated as invalid responses and removed. Fourth, participant files were merged after resolving the subject–session structure. Finally, participant-level means were computed before inferential testing to compare conditions within participants.



\## Analysis Plan



The analysis followed a structured sequence. First, descriptive statistics were computed for reaction time and accuracy across conditions. Second, Stroop interference was calculated for each participant as the difference between incongruent and congruent mean reaction times. Third, paired-samples t-tests were used to evaluate differences between conditions. Fourth, effect sizes were calculated using standardized within-subject measures. Fifth, confidence intervals were estimated for mean differences. Sixth, robustness checks were performed to assess the stability of the results. Seventh, Wilcoxon signed-rank tests were used to verify consistency with the parametric findings. Finally, a simple computational simulation was implemented to examine whether a baseline-plus-interference structure could reproduce the observed condition-level pattern.



\# Results



\## Sample and dataset summary 



The final analytic sample consisted of 81 participants. All participants contributed 

reaction time (RT) data across congruent, neutral, and incongruent conditions. Quality 

control checks displayed acceptable overall data quality, and no additional participants 

were excluded after quality control. Condition-level descriptives for reaction time and 

accuracy are reported in Table 1. 



Mean accuracy was high across all conditions, suggesting generally consistent 

task performance. Participant-level quality-control results are available in the project 

repository. No participants met the predefined exclusion criteria, and no additional 

exclusions were applied. 



Assumption checks for parametric testing are reported in the project repository. 

The distribution of the Stroop effect did not significantly deviate from normality 

(Shapiro–Wilk W = 0.971, p = 0.060). Skewness (0.410) and kurtosis (-0.573) were 

also in the acceptable ranges. They supported the assumption of approximate normality. 

Descriptive RT pattern by condition



Mean reaction times increased across conditions, with the fastest responses in the 

congruent condition and the slowest responses in the incongruent condition. Table 1 

shows that mean RT was 674 ms for congruent trials, 690 ms for neutral trials, and 778 

ms for incongruent trials. 



Figure 1 shows the distribution of participant-level reaction times across conditions, 

including variability, central tendency, and potential outliers. The observed pattern demonstrates progressively slower responses from congruent to neutral to incongruent 

trials, illustrating a clear Stroop interference effect. 



\## Descriptive accuracy pattern by condition 



Accuracy was high across all conditions, with only small differences between conditions. 

Table 1 shows that mean accuracy was 95.9% for congruent trials, 94.9% for neutral 

trials, and 93.0% for incongruent trials. At the descriptive level, there was no clear 

evidence of a speed–accuracy trade-off. 



\## Stroop effect at participant level 



The mean Stroop effect was 106.3 ms. Significant variation was observed across 

participants, as shown in Figure 2, indicating substantial individual differences in 

interference magnitude.



\## Baseline processing speed and interference 



The relationship between baseline processing speed and Stroop interference magnitude 

is shown in Figure 3. The figure compares participant-level baseline reaction times 

with individual Stroop interference scores and provides an additional perspective on 

individual differences in cognitive performance. 



\## Inferential test result 



The inferential results are summarized in Table 2. A paired-samples t-test showed a 

significant Stroop interference effect (t(80) = 17.77, p = 1.67 × 10−29).



\## Effect size and confidence interval 



The magnitude of the Stroop effect was estimated using a paired-samples approach. 

The mean difference between incongruent and congruent conditions was 106.3 ms 

across 81 participants. As shown in Table 2, the 95% confidence interval for the mean 

difference ranged from 94.6 ms to 118.1 ms. The effect was large (dz = 1.97), indicating 

strong interference at the group level. 



\## Robustness checks 



Normality of the paired difference scores was assessed using the Shapiro–Wilk test 

and additional distributional statistics. The test was non-significant (W = 0.971, p = 

0.060), and skewness (0.410) and kurtosis (-0.573) remained within acceptable ranges. 

Together, these results provided no strong evidence against the assumptions underlying 

the parametric analyses.



\## Model-vs-data comparison 



The simulation implements a minimal additive reaction-time model in which observed 

response latency is decomposed into three components: a baseline processing term, a 

condition-dependent interference term, and stochastic noise. Formally, the reaction 

time for trial i is defined as: 



𝑅𝑇𝑖 = 𝛽0 + 𝛽condition+𝜀𝑖 



where 𝛽0 represents baseline processing speed (derived from the congruent condition 

mean), 𝛽condition represents condition-specific additive costs (neutral and incongruent 

relative to congruent), and 𝜀𝑖 is Gaussian noise with standard deviation estimated from 

the empirical RT distribution. 



The model parameters were not independently fit using optimization procedures. 

They were directly derived from empirical condition means and dispersion statistics. 

As such, the model should be interpreted as a descriptive generative baseline rather 

than a mechanistic or predictive cognitive model. Its purpose is to test whether a simple 

additive structure is sufficient to reproduce observed condition-level RT patterns.



A computational simulation model was compared with the empirical RT distributions 

using a simple additive interference framework. Simulated outputs are available in the 

repository.



Figure 4 compares the empirical and simulated RT distributions. The model 

reproduces the overall Stroop pattern, with slower responses in the incongruent 

condition and faster responses in the congruent and neutral conditions.





\# Discussion



The present findings show a robust Stroop interference effect across participants. Incongruent trials produced slower reaction times and lower accuracy than congruent trials, while neutral trials consistently fell between the two conditions. This pattern was observed across 81 participants, with a large and highly reliable effect on reaction time (mean interference = 106.3 ms, t(80) = 17.77, p < 0.001, dz = 1.97). Together, these findings are consistent with the well-established behavioral pattern reported throughout the Stroop literature.



The most likely interpretation of these results is response conflict between competing stimulus representations. In incongruent trials, the automatically activated reading process conflicts with the task-relevant color-naming process, increasing processing demands and slowing response selection. Neutral trials lack direct semantic conflict and therefore produce an intermediate level of interference. Within this framework, the Stroop effect emerges from competition between parallel cognitive representations during task performance.



Alternative explanations are also possible. An attention-based account would explain the effect in terms of selective attention, where incongruent stimuli require additional processing to suppress task-irrelevant word information. A conflict-monitoring account would emphasize the detection and regulation of conflict during performance, whereas executive-control accounts interpret the effect as reflecting demands on top-down control during stimulus–response mapping. The present data do not allow us to distinguish among these explanations. The observed behavioral pattern is compatible with all three theoretical accounts.



The computational model used in this project reproduced the main pattern observed in the data: slower responses in incongruent trials, intermediate responses in neutral trials, and faster responses in congruent trials. The model represents condition differences as additive costs applied to a baseline reaction time with stochastic noise. Although simple, it demonstrates that a minimal interference framework is sufficient to reproduce the primary condition-level pattern observed in the dataset. This finding is consistent with the idea that a substantial portion of Stroop performance can be described using a small number of behavioral assumptions.



Individual differences were a notable feature of the dataset. Participants showed considerable variability in both baseline response speed and the magnitude of Stroop interference. The relationship between baseline reaction time and interference magnitude suggests that these components may be partially related rather than completely independent. This pattern highlights the importance of examining interference not only at the group level but also at the level of individual participants. Such variation may provide useful information for future studies investigating differences in cognitive control and information processing.



From a broader computational cognitive science perspective, the Stroop task remains an important paradigm for studying interference, attention, and cognitive control. The present study was not designed to resolve theoretical debates regarding the precise mechanisms underlying Stroop performance. Instead, it provides a reproducible reanalysis of open behavioral data, combining traditional statistical methods with a simple computational approach. Together, the findings show how robust behavioral effects, individual differences, and computational modeling can be integrated within a transparent and reproducible analytical framework.



\## Limitations



This study is based on secondary behavioral data and therefore does not provide direct experimental control. As a result, causal conclusions about the cognitive mechanisms underlying Stroop interference cannot be drawn. The findings are correlational and limited to the structure of the observed dataset.



Reaction time is an indirect measure of cognitive processing. It reflects the combined influence of different processes, including perceptual encoding, response selection, and motor execution. Therefore, reaction time alone cannot uniquely identify specific cognitive mechanisms. The observed Stroop effect should be interpreted as a behavioral outcome rather than a direct measure of any single process.



The dataset comes from previously collected sessions, and differences among participants cannot be fully controlled. This situation may introduce additional noise or bias into reaction time measures and estimates of individual differences.

&nbsp;	

The computational model used in this project is intentionally simple and descriptive. Its scope is limited because it does not model established cognitive mechanisms. Consequently, it cannot capture process-level dynamics underlying response selection and conflict resolution. Therefore, it should be interpreted as a minimal baseline model rather than a mechanistic account of Stroop interference.



Finally, although the dataset provides strong evidence for a Stroop interference effect at both the group and individual levels, it does not identify a single underlying cognitive mechanism. Several theoretical accounts could produce similar behavioral patterns. Therefore, the findings are consistent with Stroop interference in general, rather than supporting one specific theory.



Overall, this study demonstrates reliable behavioral interference effects and a simple computational model of those effects. However, it remains limited in terms of causal inference, mechanistic specificity, and experimental control.



\# Conclusion



This study examined cognitive interference in the Stroop task using publicly available behavioral data from 81 participants. The results showed a clear and robust Stroop effect: incongruent trials produced slower reaction times than congruent trials, while neutral trials fell between the two conditions. Accuracy remained high across conditions, suggesting that the observed effect was not driven by a simple speed–accuracy trade-off. The interference effect was large, statistically reliable, and consistent with established findings from the Stroop literature. At the individual level, substantial variation was observed in the magnitude of interference, indicating meaningful differences in performance across participants. A simple computational simulation also reproduced the main condition-level pattern observed in the empirical data. Overall, the findings are consistent with cognitive interference during response selection and demonstrate the value of reproducible behavioral analysis, individual-differences approaches, and simple computational modeling for understanding cognitive performance.



\# Acknowledgements

&nbsp;	

This project used publicly available data shared through the Open Science Framework. I thank the original contributors for making the dataset accessible for analysis and supporting open research practices. In addition, I acknowledge the open-source Python ecosystem, which made it possible to analyze, visualize, and model, as this reproducible workflow.



\# References



Botvinick, M. M., Braver, T. S., Barch, D. M., Carter, C. S., \& Cohen, J. D. (2001). Conflict monitoring and cognitive control. \*Psychological Review, 108\*(3), 624–652. https://doi.org/10.1037/0033-295X.108.3.624



MacLeod, C. M. (1991). Half a century of research on the Stroop effect: An integrative review. \*Psychological Bulletin, 109\*(2), 163–203. https://doi.org/10.1037/0033-2909.109.2.163



Parris, B. A., Hasshim, N., Wadsley, M., Augustinova, M., \& Ferrand, L. (2022). The loci of Stroop effects: A critical review of methods and evidence for levels of processing contributing to color-word Stroop effects and the implications for the loci of attentional selection. \*Psychological Research, 86\*(4), 1029–1053. https://doi.org/10.1007/s00426-021-01554-x



Scarpina, F., \& Tagini, S. (2017). The Stroop Color and Word Test. \*Frontiers in Psychology, 8\*, Article 557. https://doi.org/10.3389/fpsyg.2017.00557



Stroop, J. R. (1935). Studies of interference in serial verbal reactions. \*Journal of Experimental Psychology, 18\*(6), 643–662. https://doi.org/10.1037/h0054651

