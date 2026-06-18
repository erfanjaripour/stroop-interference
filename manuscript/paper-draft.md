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



