# Cognitive impairment in middle-aged men: a 40-year prospective study

Authors: Meder Imanaliev, Katerina Lind, Aleksandr Rakin, Ksenia Vekhova, Ivan Zarva.

Supervisors: Olga Mironenko, Ksenia Vekhova. 


## Background

Vascular dementia is considered to be the second most common subtype of dementia, after Alzheimer disease, accounting for up to 20% of dementia cases in North America and Europe [1]. In the vast majority of elderly individuals with cardiovascular diseases who develop vascular cognitive impairment (VCI), the brain shows manifestations of vascular damage or dysfunction that contribute to cognitive decline. The underlying mechanisms are not fully understood. However, the most studied one is chronic age-related dysregulation of cerebral blood flow (CBF) which includes impaired permeability of blood–brain barrier (BBB), endothelial dysfunction, and, thus, chronic hypoxia [2]. Most studies that evaluated cognitive outcomes in patients with pronounced cardiovascular damage, as is arterial hypertension, atrial fibrillation, and stroke, were focused on cohorts of older adults (aged ≥ 60 years)  [3-5]. Hence, studying a middle-aged cohort may shed a light on association of milder forms of cognitive impairment and cardiovascular events at early stage or in relatively healthy cardiovascular system. Moreover, milder forms of cognitive decline (subjective and mild cognitive impairment) may correlate with early signs of blood vessel damage, i.e. endothelial dysfunction.


## Aims and objectives

The main goal of this project is to analyze the association of cognitive impairment (CI) with variables describing cardiovascular system, emotional and affective sphere, and neuroimaging data in middle-aged Muscovite men.

The following objectives were set in order to achieve the goal:
1.	To assess the consistency of scales used in cognitive testing
2.	To identify possible predictors of CI
3.	To assess the association between CI and depression / anxiety, variables describing cardiovascular system, and other clinical data in dynamics

## Study design

The initial study design was prospective cohort observational single-center study. It started in 1984 when 23 Moscow schools were randomly selected, and 1143 boys were enrolled (average age 11.9, SD 0.11).
Over 40 years of prospective study, participants underwent 8 medical examinations with different time intervals -- before graduation from school there was an annual follow-up (Visits 1-4), later this interval was increased to 4 years (Visit 5), 
and starting from Visit 6 the interval was 8 years. During the current visit (Visit 8) the average age of participants is 51 years old. 
The main goal of initial prospective cohort study was to analyze risk factors for cardiovascular diseases from school age.

We decided to focus on cognitive performance that was assessed only during the current visit (Visit 8). Thus, the design of our final project was changed to case-control and cross-sectional.
In order to study association of cognitive performance and variables from previous visits (Visit 1-7) we chose case-control design.
There were also some variables describing MRI data and depression / anxiety inventories that were also performed on the current visit, thus, their association suggested cross-sectional design.

It is also worth mentioning to describe the algorithm for assessing cognitive performance. Participants were able to make self-reports about their cognitive decline -- memory loss -- and its duration in years. These complaints were noted as subjective cognitive decline. Apart from self-reported CI, complex neuropsychological testing was performed by a neurologist and included Montreal Cognitive Assessment (MoCA) and / or Mini–Mental State Examination (MMSE) used as screening assessment, Frontal Assessment Battery (FAB) for evaluating frontal lobe functions (executive functions), and Symbol Digit Modalities Test (SDMT) for assessing temporal and occipital lobes functions (sustained attention, processing speed), and several more tests. Participants also completed Beck Depression Inventory (BDI-II) and Spielberger-Hanin scale of reactive and personal anxiety (SRPA) in order to study their emotional and affective sphere.

If a participant reported no complaints and his cognitive tests' scores were ≥ 26 points for MoCA and / or ≥ 29 points for MMSE, his cognitive functions were considered normal (**'no CI'** group).

If a participant reported memory loss but his cognitive performance was the same as in the previous case, he was diagnosed with **subjective cognitive impairment**.

If a participant reported memory loss and his cognitive tests' scores were < 26 points for MoCA and / or < 29 points for MMSE, he was diagnosed with **mild cognitive impairment**.



## Methods

Statistical analysis was performed using R version 4.3.1 with RStudio 2023.06.1 Build 524. 
After data preprocessing, exploratory data analysis (EDA), and descriptive statistics we created directed acyclic graph (DAG) to represent possible CI predictors. 
Due to variety of used cognitive tests' scales we assessed their consistency using PCA and McNemar's test. 
In order to compare scores for depression and anxiety in 'no CI' and 'CI' groups as well as overall cognitive performance with MRI data we performed ANOVA, Spearman correlation, and ordinal logistic regression. 
To impute data on possible CI predictors we used MICE method for missing value imputation.
The association between CI and other variables in dynamics was assessed with mixed-effects models.

## Results

### Subheading 1

### Subheading 2

### Subheading 3


## Conclusions

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
