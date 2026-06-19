\# Methods



\## Participants

The dataset consisted of 85 subject-level data files from repeated behavioral recordings in a Stroop task experiment. During data integrity inspection, a mismatch between 85 files and 81 unique participants was found. It was resolved by identifying a subject–session encoding structure in the filenames, including suffix-based session markers such as “b,” which showed that some participants contributed more than one session. The dataset was then standardized by separating participant identity from session identity, resulting in a hierarchical subject–session–trial structure. No participants were excluded from the final dataset, as all files contained valid behavioral observations after preprocessing.



\## Materials / dataset

The dataset comprised trial-level behavioral responses from a computerized Stroop task. It included reaction time (RT) and accuracy measures across experimental conditions. The dataset is linked to an OSF project (reference: https://osf.io/kxpqu/overview) and contains structured experimental recordings of cognitive interference under congruent, incongruent, and neutral stimulus conditions.



\## Design

The study used a within-subject repeated-measures Stroop design. Each participant completed trials in three conditions: congruent, incongruent, and neutral. The main experimental manipulation was the level of interference between stimulus meaning and response requirements, measured through these conditions.



\## Variables

Reaction time (RT) was defined as the interval between stimulus presentation and participant response. Accuracy was coded as a correct or incorrect response on each trial. As mentioned, the condition was categorized into three levels. Participant ID defined unique subject identifiers after resolving the file-based session structure. The Stroop effect was computed at the subject level as the mean RT difference between the incongruent and congruent conditions.



\## Preprocessing

Raw data underwent several preprocessing steps before analysis. First, probe trials were removed from the dataset. Second, reaction time values below 0.20 seconds and above 2.0 seconds were excluded as unusually fast or delayed responses. Third, RT values coded as -1 were treated as invalid responses and removed. Fourth, multiple participant files were merged into a dataset after resolving the subject–session ambiguity. Finally, subject-level means were computed before inferential testing to compare conditions within participants.



\## Analysis plan

The analysis followed a structured sequence. First, descriptive statistics were computed for RT and accuracy across conditions. Second, Stroop interference was calculated for each participant as the difference between incongruent and congruent mean RTs. Third, paired-samples t-tests were used to evaluate differences between conditions. Fourth, effect sizes were calculated using standardized within-subject measures. Fifth, confidence intervals were estimated for mean differences. Sixth, robustness checks were performed to assess the stability of results under the preprocessing decisions. Seventh, Wilcoxon signed-rank tests were used where appropriate to verify consistency with the parametric results. Finally, a simple simulation model was implemented to examine whether a baseline-plus-interference structure could reproduce the observed condition means.



\# Results



\## Sample and dataset summary

The final analytic sample consisted of 81 participants. All participants contributed reaction time (RT) data across congruent, neutral, and incongruent conditions. Quality control checks displayed acceptable overall data quality, and no additional participants were excluded after quality control.

Mean accuracy rates by condition are reported in accuracy-by-condition.csv. Accuracy was high across all conditions, suggesting generally consistent task performance. Participant-level quality control results are summarized in participant-qc.csv, and no further exclusions were applied during the analysis.

Assumption checks for parametric testing are reported in assumption-checks.json. The distribution of the Stroop effect did not significantly deviate from normality (Shapiro–Wilk W = 0.971, p = 0.060). Skewness (0.410) and kurtosis (-0.573) were also within acceptable ranges, supporting the assumption of approximate normality.



\## Descriptive RT pattern by condition

Mean reaction times increased across conditions, with the fastest responses in the congruent condition and the slowest responses in the incongruent condition. Condition-level RT values are reported in rt-by-condition.csv.

Figure 1 (rt-by-condition-bar) shows the mean RT pattern across conditions and illustrates a clear Stroop interference effect. Figure 2 (rt-by-condition-box) shows the full RT distributions, including variability and outliers, suggesting that the observed condition differences were not driven by a small number of extreme observations.



\## Descriptive accuracy pattern by condition

Accuracy was high across all conditions, with only small differences between conditions. Condition-level accuracy values are reported in accuracy-by-condition.csv. At the descriptive level, there was no clear evidence of a speed–accuracy trade-off.



\## Stroop effect at participant level

Participant-level Stroop interference scores were calculated as the difference between incongruent and congruent RTs. The distribution of these scores is summarized in subject-level-stroop-effects.csv.

The mean Stroop effect was 0.1063 seconds. Considerable variation was observed across participants, as shown in Figure 5 (individual-difference-stroop-effect), suggesting that the magnitude of interference is different between individuals.

Figures 3 (stroop-effect-distribution-bar) and 4 (stroop-effect-distribution-box) provide additional summaries of the Stroop effect distribution at the group level.



\## Inferential test result

A paired-samples t-test showed a highly significant Stroop interference effect:

t(80) = 17.77, p = 1.67 × 10⁻²⁹.

The null hypothesis of no difference between incongruent and congruent reaction times was rejected.



\## Effect size and confidence interval

The magnitude of the Stroop effect was estimated using a paired-samples approach. The mean difference between incongruent and congruent conditions was 0.1063 seconds across 81 participants, with a 95% confidence interval calculated using a t-distribution-based standard error. It is reported in the analysis outputs. The effect was large and highly reliable (t(80) = 17.77, p < 10⁻²⁸, dz = 1.97), showing strong interference at the group level. Assumption checks also showed that the paired-difference distribution was approximately normal (Shapiro–Wilk W = 0.971, p = 0.060).



\## Robustness checks

Normality of the paired difference scores was assessed using the Shapiro–Wilk test and additional distributional statistics (assumption-checks.json). The test was non-significant (p = 0.060), providing no strong evidence against normality.

Skewness and kurtosis values remained within acceptable ranges for parametric analysis in a repeated-measures design. These results support the validity of the t-test results.

Overall, there was no significant evidence of non-normality that would require primary reliance on non-parametric methods.

Model-vs-data comparison

A computational simulation model was compared with the empirical RT distributions using a simple additive interference framework. Simulated outputs are provided in simulated-data.csv.

Figure 7 (model-vs-data) compares the empirical and simulated RT distributions. The model reproduces the overall Stroop pattern, with slower responses in the incongruent condition and faster responses in the congruent and neutral conditions.



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

