# Cognitive impairment in middle-aged men: a 40-year prospective study

Authors: Meder Imanaliev, Katerina Lind, Aleksandr Rakin, Ksenia Vekhova, Ivan Zarva.

Supervisors: Olga Mironenko, Ksenia Vekhova. 


## Background

Vascular dementia is considered to be the second most common subtype of dementia, after Alzheimer disease, accounting for up to 20% of dementia cases in North America and Europe [1]. In the vast majority of elderly individuals with cardiovascular diseases who develop vascular cognitive impairment (VCI), the brain shows manifestations of vascular damage or dysfunction that contribute to cognitive decline. The underlying mechanisms are not fully understood. However, the most studied one is chronic age-related dysregulation of cerebral blood flow (CBF) which includes impaired permeability of blood–brain barrier (BBB), endothelial dysfunction, and, thus, chronic hypoxia [2]. Most studies that evaluated cognitive outcomes in patients with pronounced cardiovascular damage, as is arterial hypertension, atrial fibrillation, and stroke, were focused on cohorts of older adults (aged ≥ 60 years)  [3-5]. Hence, studying a middle-aged cohort may shed light on association of milder forms of cognitive impairment and cardiovascular events at early stage or in a relatively healthy cardiovascular system. Moreover, milder forms of cognitive decline (subjective and mild cognitive impairment) may correlate with early signs of blood vessel damage, i.e. endothelial dysfunction.


## Aims and objectives

The main goal of this project is to analyze the association of cognitive impairment (CI) with variables describing cardiovascular system, emotional and affective sphere, and neuroimaging data in middle-aged Muscovite men.

The following objectives were set in order to achieve the goal:
1.	To assess the consistency of scales used in cognitive testing
2.	To identify possible predictors of CI
3.	To assess the association between CI and depression / anxiety, variables describing cardiovascular system, and other clinical data in dynamics

## Study design

The initial study design was prospective cohort observational single-center study. It started in 1984 when 23 Moscow schools were randomly selected, and 1143 boys were enrolled (average age 11.9, SD 0.11).
Over 40 years of prospective study, participants underwent 8 medical examinations with different time intervals -- before graduation from school there was an annual follow-up (Visits 1-4), later this interval was increased to 4 years (Visit 5), 
and starting from Visit 6 the interval was 8 years. During the current visit (Visit 8) the average age of participants was 50.9 years (SD 0.70).
The main goal of initial prospective cohort study was to analyze risk factors for cardiovascular diseases from school age.

We decided to focus on cognitive performance that was assessed only during the current visit (Visit 8). Thus, the design of our final project was changed to case-control and cross-sectional.
In order to study association of cognitive performance and variables from previous visits (Visit 1-7) we chose case-control design.
There were also some variables describing MRI data and depression / anxiety inventories that were also performed on the current visit, thus, their association suggested cross-sectional design.

During the current visit (Visit 8) participants underwent complex medical examination that included photoplethysmography using the Angioscan-01 computer appliance (Angioscan, Russia), 
ultrasound imaging of the main arteries (including determination of flow-mediated vasodilation (FMD)) using a Philips iE33 XMATRIX ultrasound system (Netherlands), 
applanation tonometry using SphygmoCor (AtCor Medical, West Ryde, NSW, Australia), Complete blood count and biochemical tests, office blood pressure (BP) measurement, magnetic resonance imaging (MRI), 
and neuropsychological testing.

The diagnostic algorithm for CI consisted of self-reported cognitive decline (complaints about memory loss and its duration in years) and complex neuropsychological testing (Montreal Cognitive Assessment (MoCA), 
Mini–Mental State Examination (MMSE), Frontal Assessment Battery (FAB), Symbol Digit Modalities Test (SDMT), 12-word Philadelphia Verbal Learning Test (PVLT), Verbal Association Technique (literal and categorical), Münsterberg Test, Benton Visual Retention Test, Clock Test, and Cube Drawing Test). If a participant reported no complaints and his cognitive tests' scores were ≥26 points for MoCA and/or ≥29 points for MMSE, his cognitive performance was considered normal (**'No CI'** group). If a participant reported memory loss but his cognitive performance was normal, he was diagnosed with **subjective CI**. If cognitive tests' scores were <26 points for MoCA and/or <29 points for MMSE, a participant was diagnosed with **mild CI**. 

Participants also completed Beck Depression Inventory (BDI-II) and Spielberger-Hanin scale of reactive and personal anxiety (SRPA).


## Methods

Statistical analysis was performed using R version 4.3.1 with RStudio 2023.06.1 Build 524. 
After data preprocessing, exploratory data analysis (EDA), and descriptive statistics we created directed acyclic graph (DAG) to represent possible CI predictors. 
Due to the variety of used cognitive tests' scales we assessed their consistency using PCA and McNemar's test. 
In order to compare scores for depression and anxiety in 'no CI' and 'CI' groups as well as overall cognitive performance with MRI data we performed ANOVA, Spearman correlation, and ordinal logistic regression. 
To impute data on possible CI predictors we used the MICE method for missing value imputation.
The association between CI and other variables in dynamics was assessed with mixed-effects models.

## Results

### Descriptive statistics



### PCA and McNemar's test

The consistency of cognitive tests’ scales was assessed using PCA and McNemar's test.

![Figure X. PCA Variable Correlation](data/pics/pic_4.png "Заголовок изображения")
**Figure X. PCA Variable Correlation**

![Figure X. Contribution of Variables to the First Principal Component (Dim-1)](data/pics/pic_1.png "Заголовок изображения")
**Figure X. Contribution of Variables to the First Principal Component (Dim-1)**

![Figure X. Contribution of Variables to the Second Principal Component (Dim-2)](data/pics/pic_2.png "Заголовок изображения")
**Figure X. Contribution of Variables to the Second Principal Component (Dim-2)**

Principal Component Analysis (PCA) was conducted to identify the key contributors to the variance in cognitive function indicators. The first principal component (PC1) explained 29.6% of the total variance, while the second principal component (PC2) accounted for 25.3% (Fig. X). Together, these components captured more than 50% of the total variance in the dataset.

The variable contribution plot for PC1 (Fig. X) revealed that stpersonal_v8, moca_v8, and mmse_v8 were the primary contributors to this dimension, indicating their strong influence on the overall variance structure. In contrast, symboldigit_v8, fab_v8, and benton_v8 had notably lower contributions, suggesting they played a lesser role in defining PC1.

Similarly, in PC2 (Fig. X), the highest contributing variables were stsutiational_v8, moca_v8, and stpersonal_v8, reinforcing the importance of executive and memory-related cognitive functions in shaping this component. On the other hand, symboldigit_v8 exhibited the lowest contribution to PC2, implying a relatively minor role in explaining variance in this dimension.

These findings suggest that memory and executive function variables predominantly drive the variance observed in cognitive performance across participants, while other cognitive tests contribute less significantly to the principal components.


### ANOVA, Kruskal-Wallis test, Fisher’s exact test

| **Neuropsychological testing** | **No CI** | **Subjective CI** | **Mild CI** | **p-value** | **SMD** |
| :---:        |     :---:      |    :---:      |    :---:      |    :---:      | :---: |
|    |  n=121 (68%)    |   n=42 (24%)  | n=15 (8%) | |
| 12-word Philadelphia Verbal Learning Test (PVLT) | | | | |
| PVLT Short Delay Free Recall (words)	| 10.02 (1.49) | 9.54 (1.71) |8.83 (1.51) | 0.001 | 0.507 |
| PVLT Short Delay Cued Recall (words)	|  1.82 (1.37) | 2.30 (1.65) |  3.07 (1.46) | <0.001 | 0.564 |
| PVLT Short Delay Summary (words)	| 11.84 (0.45) | 11.84 (0.37) | 11.90 (0.31) | 0.783 | 0.115 |
| PVLT Long Delay Free Recall (words)	|9.56 (1.96) | 9.54 (1.73) |  8.23 (1.77) | 0.003 | 0.488 |
| PVLT Long Delay Free Recall (words)	 | 2.20 (1.73) | 2.30 (1.70) | 3.63 (1.79) | <0.001 | 0.547 |
| PVLT Long Delay Summary (words)	| 11.75 (0.65) | 11.84 (0.55) | 11.87 (0.35) | 0.552 | 0.140 |
| Verbal Association Technique (literal) (words)	| 13.90 (4.43) | 13.16 (4.59) | 10.87 (5.14) | 0.006 | 0.422 |
| Verbal Association Technique (categorical) (words)	| 20.02 (5.31) | 19.51 (5.40) | 16.59 (3.95) | 0.006 | 0.483 |
| Münsterberg Test (words)	| 16.98 (4.43) | 19.39 (4.03) | 16.96 (5.83) | 0.022 | 0.352 |
| Benton Visual Retention Test (poins)	| 13.12 (1.42) | 13.40 (1.33) | 11.96 (1.68) | <0.001 | 0.633 |
| Clock Test (points)	|  9.61 (0.89) | 9.65 (0.54) | 8.97 (1.55) | 0.004 | 0.383 |
| Cube Drawing Test (points)	|  2.85 (0.38) | 2.92 (0.28) | 2.59 (0.68) | 0.004 | 0.441 |
| Trail-Making Test A (TMT A) (time) | 38.39 (13.94) | 38.00 (13.13) | 37.60 (8.87) | 0.952 | 0.044 |
| Trail-Making Test A (TMT A) (errors) | 0.11 (0.41) | 0.19 (0.52) | 0.30 (0.70) | 0.165 | 0.220 |
| Trail-Making Test B (TMT B) (time) | 105.61 (41.50) | 98.92 (25.54) | 121.70 (54.79) | 0.072 |  0.353 |
| Trail-Making Test B (TMT B) (errors) | 0.51 (1.00) | 0.54 (0.77) |  1.03 (1.35) | 0.044 | 0.306 |
| Symbol Digit Modalities Test (SDMT) (points)	| 45.44 (8.58) | 47.50 (7.51) | 44.60 (7.37) | 0.304 | 0.250 |
| Montreal Cognitive Assessment (MoCA) (points)	| 28.28 (1.28) | 28.12 (1.45) | 24.75 (0.45) | <0.001 | 2.311 |
| Mini–Mental State Examination (MMSE) (points)	| 28.92 (0.98) | 28.91 (1.13) | 26.66 (1.59) | <0.001 | 1.121 |
| Frontal Assessment Battery (FAB) (points)	| 17.42 (0.90) | 17.24 (1.13) | 16.25 (1.58) | <0.001 | 0.606 |
| Spielberger-Hanin scale of reactive anxiety (SRPA) (points)	| 35.60 (7.77) | 37.51 (7.92) | 38.89 (9.04) | 0.111 | 0.265 |
| Spielberger-Hanin scale of personal anxiety (SRPA) (points)	| 38.31 (7.34) | 39.56 (9.03) | 43.92 (8.60) | 0.005 | 0.449 |
| Beck Depression Inventory (BDI) (points)	|  6.64 (4.68) | 8.67 (5.30) |  9.62 (7.85) | 0.015 | 0.337 |

**Table 1. Comparison of scores for neuropsychological tests in CI groups**

| **MRI data** | **No CI** | **Subjective CI** | **Mild CI** | **p-value** | **SMD** |
| :---:        |     :---:      |    :---:      |    :---:      |    :---:      |  :---:      |
|    |  n=121 (68%)    |   n=42 (24%)  | n=15 (8%) | |
| Several vascular lesions 	  |  51 (46.8%)  |   13 (34.2%) |  11 (37.9%) | 0.344 | 0.172 |
| Multiple vascular lesions 	|    20 (18.3%)  |   6 (15.8%) |  5 (17.2%) | 0.937 | 0.045 |
| Perivascular spaces (PV spaces) enlargement	 |   15 (13.8%) |  5 (13.2%) | 9 (31.0%) | 0.069 |0.294 |
| Cerebrovascular fluid (CVF) spaces enlargement	|    22 (20.2%) | 10 (26.3%) | 6 (20.7%) | 0.725 | 0.097|
| Lacunes  |	3 (2.8%) | 0 (0.0%) | 0 (0.0%) | 0.391 | 0.159 |
| Subcortical white matter infarcts	 |  0 (0.0%) | 0 (0.0%) | 2 (6.9%) | 0.006 | 0.257 |
| Hippocampal lesions	 | 3 (2.8%) | 0 (0.0%) | 1 (3.4%) | 0.555 | 0.182|

**Table 2. Associations between MRI data and CI groups**


| **Endothelium function and arterial stiffness** | **No CI** | **Subjective CI** | **Mild CI** | **p-value** |
| :---:        |     :---:      |    :---:      |    :---:      |    :---:      |
|    |  n=121 (68%)    |   n=42 (24%)  | n=15 (8%) | |
| Celermajer test (%)	|  7.35 (3.68)	|  7.09 (3.65)	|  7.32 (2.35)	| 0.925 |
| Pharmacological test index (amplitude)	|  1.90 (0.68)	|  1.90 (0.43)	|  1.75 (1.56)	| 0.763 |
| Pharmacological test index (phase)	| -7.02 (5.23)	| -8.02 (6.48)	| -6.15 (3.73) |	0.467 |
| Heart rate, beats/min	| 70.29 (10.71)	| 67.53 (12.44)	| 76.46 (14.90)	| 0.054 |
| Augmentation index adjusted to 75 bpm (%)	|  4.23 (12.26)	|  2.86 (10.90)	 | 9.42 (9.66)	| 0.223 |
| Vascular age (years)	| 50.10 (11.01)	| 48.50 (7.59)	| 53.85 (8.88)	| 0.264 |
| Oxygen saturation (%)	| 94.55 (2.24)	| 94.91 (1.59)	| 93.70 (1.43)	| 0.194 |
| Augmentation index (peripheral) (%)	|  6.94 (16.38)	|  6.65 (13.01)	|  7.89 (10.45)	| 0.969 |
| Stiffness index (m/s)	 | 7.91 (0.85)	|  7.89 (0.68)	|  8.19 (0.90)	| 0.476 |
| Ejection duration (%)	| 35.09 (4.25)	| 34.32 (4.27)	| 35.08 (5.84)	| 0.637 |
| Alternative vascular stiffness index (m/s)	|  8.03 (1.70)	|  7.62 (1.69)	| 10.02 (3.36)	|<0.001 |
| Reflection index (%)	| 32.97 (13.06)	| 29.89 (8.90)	| 34.42 (11.69)	| 0.33 |
| Ejection duration (ms)	| 302.33 (20.74)	| 307.97 (26.11)	| 278.92 (29.80)	| <0.001 |
| Pulse wave duration (ms)	| 873.28 (128.86)	| 914.61 (154.97)	| 815.15 (169.59)	| 0.068 |
| Time to 1st peak (peripheral) (ms)	| 112.88 (9.87)	| 110.21 (19.50)	| 106.92 (18.58)	| 0.223 |
| Time to 2nd peak (peripheral) (ms)	| 227.05 (20.22)	| 233.32 (24.52)	| 206.62 (27.89)	| 0.001 |
| dTpp (ms)	| 113.93 (19.61)	| 120.47 (21.70)	|  96.62 (26.18)	|0.002 |
| Central systolic pressure (predicted) (mmHg)	| 130.95 (16.54)	| 128.24 (20.43)	| 130.00 (17.16)	| 0.709 |
| Time of maximum rate of capillary blood filling (ms)	| 39.44 (6.31)	| 39.13 (4.67)	| 38.31 (3.47)	| 0.786 |
| Pulse wave amplitude	|  3.02 (0.89)	|  3.14 (0.73)	|  3.26 (0.81)	| 0.517 |

**Table 3. Associations between clinical data and CI groups**


To compare scores for neuropsychological assessment in CI groups and the associations between cognitive function and MRI and clinical data, we performed ANOVA analysis. Groups were compared using the Kruskal-Wallis test for continuous variables and Fisher’s exact test for categorical variables.


### Missing value imputation method (MICE)

Only the target variables (**MMSE, MoCA, FAB, SymbolDigit, SRPA, and BDI**) and dependent variables (anthropometric measurements, blood pressure, biochemical markers, and other predictors) were retained from the entire dataset for further analysis. The data were preprocessed by removing records with missing values in key cognitive variables. The dataset was filtered to include only observations where at least one of the target variables and predictors had valid data. 

The missing data structure was analyzed using the md.pattern() function, which visualizes missing value patterns. Before imputation, **14.09% of the data were missing** (1666 values in total). An imputation matrix was constructed to determine which variables were used to restore missing values. In this matrix, target variables were not imputed but used as predictors, while the identifier (id) was completely excluded from the process. Only predictor variables (anthropometric, biochemical, and physiological indicators) were included in the imputation, with 10 iterations and 10 imputed datasets. 

The **Predictive Mean Matching (PMM) method**, implemented in the mice package in R, was used to fill in the missing values. To reduce multicollinearity, height measurements from visits 5 to 8 were averaged into a single variable. This adjustment was necessary because growth curves plateau after the age of 30, making individual height measurements highly correlated. By computing the mean height across these visits, we minimized redundancy in the dataset while preserving essential variability in height-related factors. This approach ensured a more stable statistical model and improved the interpretability of regression analyses.

![Figure X. Missing patterns before imputation](data/pics/pic_7.png "Заголовок изображения")
**Figure X. Missing patterns before imputation**
![Figure X. Missing patterns after imputation](data/pics/pic_8.png "Заголовок изображения")
**Figure X. Missing patterns after imputation**

### Mixed-effects models

The association between CI and variables from previous visits in dynamics was assessed using mixed-effects models. We used clinical data regarding cardiovascular system (systolic and diastolic blood pressure (SBP and DBP respectively) and pulse), atherogenic coefficient ((total cholesterol-high-density lipoprotein cholesterol (HDLc))/HDLc), and body mass index (BMI) (weight (kg)/height^2 (meters)).

![Figure X. LMM results for systolic blood pressure data](data/pics/LMM_analysis/ft_sbp.png "Заголовок изображения")
**Figure X. LMM results for systolic blood pressure data**

![Figure X. LMM results for pulse data](data/pics/LMM_analysis/ft_pulse.png "Заголовок изображения")
**Figure X. LMM results for pulse data**

![Figure X. LMM results for diastolic blood pressure data](data/pics/LMM_analysis/ft_dbp.png "Заголовок изображения")
**Figure X. LMM results for diastolic blood pressure data**

![Figure X. LMM results for Body Mass Index data](data/pics/LMM_analysis/ft_bmi.png "Заголовок изображения")
**Figure X. LMM results for Body Mass Index data**

![Figure X. LMM results for atherogenic coefficient data](data/pics/LMM_analysis/ft_athero_index.png "Заголовок изображения")
**Figure X. LMM results for atherogenic coefficient data**

The LMM analysis revealed that none of the included cardiovascular parameters demonstrated a significant association with cognitive or psychological outcomes. Specifically:

1) Systolic Blood Pressure (Fig.X): No statistically significant relationship was found between SBP across visits and cognitive outcomes, as indicated by non-significant F-values (all p>0.05).

2) Diastolic Blood Pressure (Fig.X): Similar to SBP, DBP did not show any meaningful association with CI or psychological measures over time (all p>0.05).

3) Pulse(Fig.X): The analysis did not detect any significant effect of pulse rate on cognitive function or psychological outcomes (all p>0.05).

4) Atherogenic Coefficient (Fig.X): No significant associations were observed between the atherogenic coefficient and cognitive impairment, suggesting no detectable impact of lipid profile dynamics on cognitive status (all p>0.05).

5) Body Mass Index (Fig.X): Changes in BMI over time were not significantly linked to cognitive or psychological outcomes (all p>0.05).

These findings suggest that fluctuations in cardiovascular parameters and metabolic factors over time do not significantly contribute to cognitive impairment in this cohort. The results indicate that other factors may play a more prominent role in the progression of cognitive decline, warranting further investigation.

## Conclusions

The study included 178 men, 121 of which had normal cognitive performance – ‘no CI’ group (68%), 42 men were diagnosed with subjective CI (24%), and 15 participants had mild CI (8%). The results of PCA demonstrated a high contribution of BDI and SRPA to the main components (Dim-1 and Dim-2). Statistically significant difference (p<0.05) in cognitive performance between groups with no CI, subjective CI, and mild CI was found for the following cognitive tests: 12-word Philadelphia Verbal Learning Test (PVLT) for Long Delay Free Recall and Cued Recall, Verbal Association Technique (categorical), Clock Test, Cube Drawing Test, Benton Visual Retention Test, MoCA, MMSE, and FAB. Association between CI and MRI data was present in two participants with mild CI who had subcortical white matter infarcts (p<0.001). In the endothelium function and arterial stiffness panel, statistically significant difference (p<0.05) between groups was present for the following variables: alternative vascular stiffness index, ejection duration, time to 2nd peak (peripheral), and dTpp. None of the predictors (systolic and diastolic BP, pulse, body mass index, and atherogenic coefficient) investigated in linear mixed-effects models showed statistically significant associations with cognitive outcomes based on the D1 test results.

The high contribution of BDI and SRPA inventories to cognitive performance may be attributed to the reciprocal influence of emotional and affective factors on cognitive functions. The cognitive tests showing statistically significant differences between groups include not only screening assessments (MoCA and MMSE) but also more specialized tests evaluating memory, visual perception, associative thinking, executive functions, and spatial perception, which cannot be fully assessed using screening scales alone. Hence, due to the fact that cognitive decline in middle-aged men is not so pronounced, precise tests should be used for more detailed examination. Association between mild CI and morphologic changes on MRI was present in two of 15 men in this group (13.33%). Thus, neurovisualization cannot be used as the main method for detecting subjective and mild CI; however, MRI findings may provide evidence for organic changes in the brain, especially those of vascular etiology. We suggest that diagnostic algorithm for non-dementia stages of CI should include both complex neuropsychological testing as well as neurovisualization.

## Limitations
* Single-center study
* No exact information on CI onset and its dynamics
* Irregular intervals between visits (up to 8 years after participants had graduated from school)
* Cohort specificity (same sex and age)
* Low CI prevalence for this age group
* Loss to follow-up -> no updates on patients’ status, medical history, and reasons for dropout (esp. death)
* Missing values

These limitations forced us to change study design from initial cohort study to case-control study with elements of cross-sectional analysis.


## References:
1.	Rizzi L, Rosset I, Roriz-Cruz M. Global epidemiology of dementia: Alzheimer’s and vascular types. Biomed Res Int. 2014;2014:908915. doi: 10.1155/2014/908915
2.	Zlokovic BV, Gottesman RF, Bernstein KE, et al. Vascular contributions to cognitive impairment and dementia (VCID): A report from the 2018 National Heart, Lung, and Blood Institute and National Institute of Neurological Disorders and Stroke Workshop. Alzheimers Dement. 2020;16(12):1714-1733. doi:10.1002/alz.12157
3.	Qiu C, Winblad B, Fratiglioni L. The age-dependent relation of blood pressure to cognitive function and dementia. Lancet Neurol. 2005;4(8):487-499. doi:10.1016/S1474-4422(05)70141-1
4.	Ding M, Fratiglioni L, Johnell K, et al. Atrial fibrillation, antithrombotic treatment, and cognitive aging: A population-based study. Neurology. 2018;91(19):e1732-e1740. doi:10.1212/WNL.0000000000006456
5.	Srithumsuk W, Kabayama M, Gondo Y, et al. The importance of stroke as a risk factor of cognitive decline in community dwelling older and oldest peoples: the SONIC study. BMC Geriatr. 2020;20(1):24. Published 2020 Jan 22. doi:10.1186/s12877-020-1423-5
