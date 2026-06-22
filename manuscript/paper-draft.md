\# Abstract



The Stroop task is a classic paradigm for studying cognitive interference, selective attention, and response competition. By analyzing behavioral data from 81 participants, this study examined how congruent, incongruent, and neutral conditions affect reaction time and accuracy. The dataset contained trial-level responses from a publicly available Stroop experiment. In the preprocess, probe trials, invalid reaction times, and extreme values were removed. In addition, the participant–session structure in the raw files was resolved. The results showed a robust Stroop interference effect. The fastest reaction times were in the congruent condition, and the slowest in the incongruent condition. The neutral condition contained intermediate performances. The mean interference effect is defined as the difference in reaction time between incongruent and congruent trials. It was 0.106 seconds. A paired-samples t-test confirmed a significant difference between incongruent and congruent conditions, with t(80) = 17.77, p < .001, and a large effect size (dz = 1.97). It showed strong interference at the group level. Accuracy remained high across conditions, with little evidence of a speed–accuracy trade-off. Assumption checks supported the use of parametric analysis.



\# Introduction



The Stroop task is one of the widely used paradigms for studying cognitive interference, selective attention, and cognitive control. In the classic color-word version of the Stroop task, participants are required to identify the ink color of a stimulus while ignoring its semantic content.  When the word meaning conflicts with the ink color, for instance, the word ‘RED’ printed in blue ink, performance is generally slower and less accurate than when the meaning and the color are consistent. This phenomenon is known as the Stroop effect. It was first systematically documented by Stroop (1935) and thereafter became a central tool for studying how competing sources of information influence behavior. Decades of research have indicated that the Stroop effect is robust across a wide range of experimental settings and populations. Indeed, it became one of the most reliable findings in cognitive psychology (MacLeod, 1991). The Stroop task, in both experimental and applied contexts, remains a standard measure of cognitive interference and inhibitory control (Scarpina \& Tagini, 2017).

&nbsp;	

Although the behavioral pattern itself is well established, its underlying cognitive cause remains the subject of theoretical debate. Early accounts emphasized automaticity, suggesting that reading is a highly practiced process, and it is difficult to suppress when participants are instructed to name ink colors. Other approaches have focused on selective attention and the allocation of processing resources to task-relevant information. More recent theories emphasize response conflict and cognitive control mechanisms. In conflict-monitoring frameworks, interference arises because competing representations activate incompatible responses; as a result, for control processes that regulate behavior, it increases the demand (Botvinick et al., 2001). At the same time, contemporary reviews argue that Stroop interference cannot be attributed to a single processing stage and may reflect contributions from perceptual, semantic, and response-level sources of conflict. Consequently, important questions remain about the exact origins of the effect and the interpretation of behavioral measures that are caused by Stroop performance (Parris et al., 2021).

&nbsp;	

Building on this literature, the present study adopts a data-driven and reproducible analytical approach rather than attempting to adjudicate between competing theoretical accounts. Using an openly available trial-level dataset, the study quantifies Stroop interference across congruent, incongruent, and neutral conditions, examines inter-individual variability in interference magnitude, and evaluates whether a simple additive baseline-plus-interference model can account for observed behavioral patterns. In addition to group-level estimates of reaction time and accuracy effects, the analysis characterizes variability across participants, providing a more fine-grained description of performance than condition averages alone.

&nbsp;	

The primary aim of the study is to examine the impact of cognitive interference on reaction time and accuracy in the Stroop task. It is hypothesized that incongruent trials will produce slower responses than congruent trials, with neutral trials yielding intermediate performance. A secondary aim is to quantify individual differences in interference magnitude. Finally, a simple computational model is used to evaluate whether an additive structure can reproduce the main behavioral effects observed in the empirical data. Together, these analyses provide a transparent and reproducible characterization of Stroop performance while illustrating how behavioral analysis and computational modeling can be integrated within a unified framework.



\# Methods



\## Participants



The dataset consisted of 85 subject-session files corresponding to 81 unique participants. Inspection of file identifiers revealed a hierarchical structure in which some participants contributed multiple recording sessions. To resolve this, participant identity and session identity were explicitly separated, yielding a subject–session–trial data structure. All analyses in this manuscript were conducted at the participant level by aggregating trials across sessions within each participant. Sessions were not treated as independent statistical units, and no participant was excluded on the basis of having multiple sessions. This aggregation ensures that inferential statistics respect the independence assumption at the participant level while retaining all available trial-level observations.



\## Materials / dataset



The dataset comprised trial-level behavioral responses from a computerized Stroop task. It included reaction time (RT) and accuracy measures across experimental conditions. The dataset is linked to an OSF project (reference: https://osf.io/kxpqu/overview) and contains structured experimental recordings of cognitive interference under congruent, incongruent, and neutral stimulus conditions.



\## Design



The study used a within-subject Stroop design with repeated measures. Each participant did trials in congruent, incongruent, and neutral conditions. The main experimental manipulation was the interference between stimulus meaning and response requirements, which was measured through these conditions.



\## Variables



Reaction time (RT) was defined as the interval between stimulus presentation and participant response. Accuracy was coded as a correct or incorrect response on each trial. As mentioned, the condition was categorized into three levels. Participant ID defined unique subject identifiers after resolving the file-based session structure. The Stroop effect was computed at the subject level and the mean RT difference between the incongruent and congruent conditions.



\## Preprocessing



Raw data underwent several preprocessing steps before analysis. First, probe trials were removed from the dataset. Second, reaction time values below 0.20 and above 2.0 seconds were excluded as unusually fast or delayed responses. Third, RT values coded as -1 were treated as invalid responses and removed. Fourth, multiple participant files were merged into a dataset after resolving the subject–session ambiguity. Finally, subject-level means were computed before inferential testing to compare conditions within participants.



\## Analysis plan



The analysis followed a structured sequence. First, descriptive statistics were computed for RT and accuracy across conditions. Secondly, Stroop interference was calculated for each participant as the difference between incongruent and congruent mean RTs. Third, paired-samples t-tests were used to evaluate differences between conditions. Fourth, effect sizes were calculated using standardized within-subject measures. Fifth, confidence intervals were estimated for mean differences. Sixth, robustness checks were performed to assess the stability of results under the preprocessing decisions. Seventh, Wilcoxon signed-rank tests were used to verify consistency with the results. And finally, a simple simulation model was added to examine whether a baseline-plus-interference structure could reproduce the observed condition means.



\# Results



\## Sample and dataset summary



The final analytic sample consisted of 81 participants. All participants contributed reaction time (RT) data across congruent, neutral, and incongruent conditions. Quality control checks displayed acceptable overall data quality, and no additional participants were excluded after quality control.



Mean accuracy rates by condition are reported in accuracy-by-condition.csv. Accuracy was high across all conditions, suggesting generally consistent task performance. Participant-level quality control results are summarized in participant-qc.csv, and no further exclusions were applied during the analysis.



Assumption checks for parametric testing are reported in assumption-checks.json. The distribution of the Stroop effect did not significantly deviate from normality (Shapiro–Wilk W = 0.971, p = 0.060). Skewness (0.410) and kurtosis (-0.573) were also in the acceptable ranges. They supported the assumption of approximate normality.



\## Descriptive RT pattern by condition



Mean reaction times increased across conditions, with the fastest responses in the congruent condition and the slowest responses in the incongruent condition. Condition-level RT values are reported in rt-by-condition.csv.

Figure 1 (rt-by-condition-bar) shows the mean RT pattern across conditions and illustrates a clear Stroop interference effect. Figure 2 (rt-by-condition-box) shows the full RT distributions, including variability and outliers, suggesting that the observed condition differences were not driven by a small number of extreme observations.



\## Descriptive accuracy pattern by condition



Accuracy was high across all conditions, with only small differences between conditions. Condition-level accuracy values are reported in accuracy-by-condition.csv. At the descriptive level, there was no clear evidence of a speed–accuracy trade-off.



\## Stroop effect at participant level



Participants' Stroop interference scores were calculated as the difference between incongruent and congruent reaction times. The distribution of these scores is summarized in subject-level-stroop-effects.csv. The mean Stroop effect was 0.1063 seconds. Significant variation was observed across participants. It is shown in Figure 5 (individual-difference-stroop-effect). It suggested that the magnitude of interference is different across individuals. Figures 3 (stroop-effect-distribution-bar) and 4 (stroop-effect-distribution-box) provide additional summaries of the Stroop effect distribution at the group level.



\## Inferential test result



Paired-samples t-test showed a significant Stroop interference effect (t(80) = 17.77, p = 1.67 × 10⁻²⁹). The null hypothesis, which states that there is no difference between incongruent and congruent reaction times, was rejected.



\## Effect size and confidence interval



The magnitude of the Stroop effect was estimated using a paired-samples approach. The mean difference between incongruent and congruent conditions was 0.1063 seconds across 81 participants. A 95% confidence interval was also calculated using a t-distribution-based standard error. It is reported in the analysis outputs. The effect was large and highly reliable (t(80) = 17.77, p < 10⁻²⁸, dz = 1.97). Showing strong interference at the group level. Assumption checks also showed that the paired-difference distribution was approximately normal (Shapiro–Wilk W = 0.971, p = 0.060).



\## Robustness checks



Normality of the paired difference scores was assessed by using the Shapiro–Wilk test and additional distributional statistics (assumption-checks.json). The test was non-significant (p = 0.060), and it provided no strong evidence against normality. Skewness and kurtosis values also remained within acceptable ranges for parametric analysis in a repeated-measures design. These results support the validity of the t-test results. Overall, there was no significant evidence of non-normality.



\## Model-vs-data comparison



The simulation implements a minimal additive reaction-time model in which observed response latency is decomposed into three components: a baseline processing term, a condition-dependent interference term, and stochastic noise. Formally, the reaction time for trial i is defined as:



RTᵢ = β₀ + β\_condition + εᵢ



where β₀ represents baseline processing speed (derived from the congruent condition mean), β\_condition represents condition-specific additive costs (neutral and incongruent relative to congruent), and εᵢ is Gaussian noise with standard deviation estimated from the empirical RT distribution.



The model parameters were not independently fit using optimization procedures. They were directly derived from empirical condition means and dispersion statistics. As such, the model should be interpreted as a descriptive generative baseline rather than a mechanistic or predictive cognitive model. Its purpose is to test whether a simple additive structure is sufficient to reproduce observed condition-level RT patterns.



A computational simulation model was compared with the empirical RT distributions using a simple additive interference framework. Simulated outputs are provided in simulated-data.csv.

Figure 7 (model-vs-data) compares the empirical and simulated RT distributions. The model reproduces the overall Stroop pattern, with slower responses in the incongruent condition and faster responses in the congruent conditions and the neutral conditions.



\## Tables and figures reference summary



Table 1: Condition-level descriptives (RT and accuracy) (table1-descriptives.csv)

Table 2: Inferential statistics for the Stroop effect (table2-inferential-results.csv)

Figure 1: rt-by-condition-bar

Figure 2: rt-by-condition-box

Figure 3: stroop-effect-distribution-bar

Figure 4: stroop-effect-distribution-box

Figure 5: individual-difference-stroop-effect

Figure 6: baseline-vs-effect

Figure 7: model-vs-data



\# Discussion



The present findings show a robust Stroop interference effect across participants. Incongruent trials produced significantly slower reaction times and lower accuracy than congruent trials, while neutral trials consistently fell between the two conditions. This pattern was stable across the sample, within 81 participants, with a large and highly reliable effect on reaction time (mean interference = 0.106 s, t(80) = 17.77, p < 0.001, dz = 1.97). Assumption checks showed no significant deviation from normality in the within-subject effect distribution (Shapiro–Wilk W = 0.971, p = 0.060), with only mild positive skewness (0.41) and slight platykurtosis (-0.57), supporting the use of parametric tests.



The most likely interpretation of these results is response conflict between competing stimulus representations. In incongruent trials, the automatically activated reading process conflicts with the task-relevant color-naming process, making decisions more difficult and slowing response selection. Neutral trials lack direct semantic conflict and therefore reduce, but do not eliminate, processing demands, resulting in an intermediate level of interference. Within this framework, the Stroop effect emerges from competition between parallel cognitive representations during response selection.



Alternative explanations are also possible and cannot be distinguished by the present analysis. An attention-based account would explain the effect in terms of attentional allocation, where incongruent stimuli require additional selective attention to suppress irrelevant word information. A conflict-monitoring account, within the framework of adaptive control theories, would emphasize the regulation of cognitive control following conflict detection, potentially influencing later performance in addition to immediate reaction times. Executive-control accounts similarly interpret the effect as reflecting limitations in top-down control during stimulus-response mapping. The present data do not allow us to distinguish among these explanations. At the behavioral level, the findings are consistent with all three, highlighting that it is difficult to infer cognitive mechanisms from aggregate reaction-time measures alone.



The computational model used in this project captures the main pattern in the data, which is slower responses in incongruent trials, intermediate responses in neutral trials, and faster responses in congruent trials. However, it should not be considered a mechanistic model of cognitive processing. Instead, it represents differences of conditions as additive costs applied to a baseline reaction time with stochastic noise. The model reproduces only mean-level effects. As a result, its explanatory power is limited to describing the observed pattern rather than explaining the underlying cognitive processes.



Individual differences were a notable feature of the dataset and cannot be fully captured by group-level effects. Participants showed significant variability in both baseline response speed and the strength of Stroop interference, showing differences in sensitivity to interference. This pattern suggests that cognitive control efficiency and processing speed may be partially independent constructs. In addition, unequal trial counts across participants and conditions introduced differences in measurement reliability, meaning that some individual estimates are likely more reliable than others. These observations highlight the importance of viewing interference not only as a group-level effect but also as a distribution of effects across individuals.



From a computational perspective, the Stroop task remains a classic paradigm for studying conflict between competing internal representations. It provides a controlled setting for evaluating theories of selective attention, response selection, and cognitive control. Although the model used here is intentionally simple, it shows how a behavioral cognitive phenomenon can occur from a small set of simple assumptions. More advanced approaches, such as sequential sampling models or conflict-monitoring frameworks, would be needed to model temporal dynamics, learning effects, and full reaction-time distributions. Despite its simplicity, the model represents the core structure of cognitive interference. It provides a foundation for more advanced approaches.



\# Limitations



This study is based on secondary behavioral data and therefore does not provide direct experimental control. As a result, causal conclusions about the cognitive mechanisms underlying Stroop interference cannot be drawn. The findings are correlational and limited to the structure of the observed dataset.



Reaction time is an indirect measure of cognitive processing. It reflects the combined influence of different processes, including perceptual encoding, response selection, and motor execution. Therefore, reaction time alone cannot uniquely identify specific cognitive mechanisms. The observed Stroop effect should be interpreted as a behavioral outcome rather than a direct measure of any single process.



The dataset comes from previously collected sessions, and differences among participants cannot be fully controlled. This situation may introduce additional noise or bias into reaction time measures and estimates of individual differences.



The computational model used in this project is intentionally simple and descriptive. Its scope is limited because it does not model established cognitive mechanisms. Consequently, it cannot capture process-level dynamics underlying response selection and conflict resolution. Therefore, it should be interpreted as a minimal baseline model rather than a mechanistic account of Stroop interference.



Finally, although the dataset provides strong evidence for a Stroop interference effect at both the group and individual levels, it does not identify a single underlying cognitive mechanism. Several theoretical accounts could produce similar behavioral patterns. Therefore, the findings are consistent with Stroop interference in general, rather than supporting one specific theory.



Overall, this study demonstrates reliable behavioral interference effects and a simple computational model of those effects. However, it remains limited in terms of causal inference, mechanistic specificity, and experimental control.

