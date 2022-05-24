# CPRD_multimorbidity_codelists

This repository shares the code lists for our analysis of trends in multimorbidity between 2004 - 2019 in England, using CPRD Aurum data. 
 
We adapted code lists from the CALIBER algorithms, available here https://www.caliberresearch.org/portal/phenotypes/chronological-map and in machine-readable format here https://github.com/spiros/chronological-map-phenotypes. These code lits were used in Kuan, V. et al. (2019) ‘A chronological map of 308 physical and mental health conditions from 4 million individuals in the English National Health Service’, The Lancet Digital Health. Elsevier Ltd, 1(2), pp. e63–e77. https://doi.org/10.1016/S2589-7500(19)30012-3 

Our study uses the following multimorbidity definitions:
Basic multimorbidity - two or more chronic diseases. 
Complex multimorbidity - “three or more chronic conditions affecting three or more different body systems” (Harrison, C. et al. 2014. ‘Examining different measures of multimorbidity, using a large prospective cross-sectional study in Australian general practice’, BMJ Open. https://doi.org/10.1136/bmjopen-2013-004694.)

We applied the Academy of Medical Sciences definition of chronic conditions to the CALIBER lists: 
“A physical non-communicable disease of long duration, such as a cardiovascular disease or cancer; 
A mental health condition of long duration, such as a mood disorder or dementia; 
or an infectious disease of long duration, such as HIV or hepatitis C”. 
We used long-term and active as the two criteria in assessing which conditions were of long duration. 
Active was defined as either i) using resources/impacting health, ii) conditions (e.g. cancer) that affect the subsequent risk of other conditions. 
(The Academy of Medical Sciences. Multimorbidity: a priority for global health research. 2018.)

As CALIBER code lists were developed using the GPRD GOLD database, a mapping process is required in order to use these in the Aurum CPRD database. 
The mapping process was done for our specific  study of trends in multimorbidity over time, and is by no means a definitive list. Mapping was done using the July 2020 Aurum dictionary. 1 clinician reviewed the additional codes mapped. 

## This repository contains the following files:
1. DiseaseSummary.csv - this is a list of chronic conditions of interest for our study, narrowed down from the 308 diseases phenotypes by CALIBER. 'Disease' is condition the name in the CALIBER list, 'Disease_mod' is our amended name. The variables 'disease_num' & 'system_num'  are arbitrary variables for ease of coding. 'type' refers to whether a single code ever recorded is sufficient, or whether a multivisit criteria (at least 3 visits within 1 year) is required; conditions with an empty type are from test values only. 'testvalues' (yes/no) is for whether test values are used for this condition. 
2. codelists - .csv files for each disease - codes for test results are in the 'tests' subfolder. the 'mapping' column is how the Aurum code was derived from the CALIBER GOLD lists:
a. cleansedreadcode - GOLD Read code matched Aurum 'cleansedreadcode'
b. originalreadcode - GOLD Read code matched Aurum 'originalreadcode'
c. description - GOLD description matched Aurum 'term' 
d. termsearch - codes identified by searching Aurum for similar terms to original CALIBER GOLD list
3. DiseaseDocumentation - this shows the codelists along with notes on implementation. The .md file is too large to be rendered in github, a .html version can be viewed here: https://annalhead.github.io/CPRD_multimorbidity_codelists/docs/DiseaseDocumentation.html 


## Additional notes:

In our final analyses, we merged the following CALIBER categories into one category, as they represent progression of a single condition. This resulted in a final list of 211 conditions
1. Atrioventricular block first degree, Atrioventricular block second degree, Atrioventricular block third degree --> Atrioventicular blocks
2. Chronic Kidney Disease (stages 3-4); End Stage Renal Disease --> Chronic Kidney Disease
3. Right bundle branch block; Bifascicular block; Trifascicular block --> Right bundle branch block combinations

We developed our condition list amending previously derived codes to ensure only chronic presentations of conditions were included. For conditions that have both acute and chronic presentations, we included only cases with three or more relevant codes recorded within a one-year period. 

We removed all “history of” / “H/O” codes, on the assumption that other observations would be recorded if the condition was an ‘active’ health problem.

For conditions (e.g. reflux uropathy) which are commonly resolved in childhood, we excluded diagnoses before the age of 18.  

Our definition of multimorbidity included sequalae of certain conditions, e.g. diabetes and diabetic neuropathy, and did not allow ‘recovery’ from a condition. We chose to include these because of the differing impact on health outcomes associated with coexistence of sequalae, and of the likely impact of these conditions on future health, to healthcare usage, or to future risk of ill health. 

