### Data Handling Rationale

We looked at each column's description on the NSCH topical variable descriptions as well as the breakdown of values in the 2020 data to determine how each column should be handled. The following is our rationale for each column.

K2Q35A, K2Q35A_1_YEARS, K2Q35B, AUTISMMED, AUTISMTREAT, K2Q35C, K2Q35D: ASD information, not usable to predict if the child has ASD.

FIPSST: State identifier; dropped, location isn't a factor we're interested in exploring.

STRATUM: Sampling stratum; dropped, not relevant

HHID: Unique household identifier; dropped, not relevant

FORMTYPE: Indicated the age of the child; T1 is a 0-5 year old, T2 is a 6-11 year old, T3 is a 12-17 year old. Dropped, we're more interested in specific age than the general age range this column gives.

TOTKIDS_R: Total number of children in household. Needs no preprocessing.

TENURE: Indicates home onwership status; could be made categorical rather than numeric, but dropped for initial pass

HHLANGUAGE: Indicates language spoken in the household. Few enough null values to impute with mode, indicating english speaking household.

SC_AGE_YEARS: Age of child in years, no preprocessing needed

SC_SEX: Sex of child, no preprocessing needed

BIRTH_MO, BIRTH_YR: Indicates when the child was born. No preprocessing needed

BMICLASS: Body mass index of the child. Dropped since it was null 49% of the time

MOMAGE: Age of the mother when the child was born. Imputed with median.

K6Q41R_STILL: Indicates if the child is still breastfeeding, dropped since it's not applicable to older children.

K6Q42R_NEVER: Indicates when the child was first fed formula, dropped since it's not applicable to older children.

K6Q43R_NEVER: Indicates when the child was first fed anything other than formula or breastfed, dropped since not applicable to older children.

K6Q13A, K6Q13B, K6Q14A, K6Q14B, K6Q12: Questions about questionaires from the child's doctor. Dropped since not applicable to older children.

K4Q32X01, K4Q32X02, K4Q32X03, K4Q32X04, K4Q32X05: Questions indicating where the child had their eyes tested. Boolean columns imputed with no.

DENTALSERV1, DENTALSERV2, DENTALSERV3, DENTALSERV4, DENTALSERV5, DENTALSERV6, DENTALSERV7: Questions indicating what dental visits the child had; boolean columns imputed with no.

K4Q28X01, K4Q28X02, K4Q28X03, K4Q28X_EAR, K4Q28X04, K4Q28X05: Indicates child needed healthcare that was not recieved; boolean column imputed with no.

SESPLANYR, SESPLANMO: Indicates age child started a special ed program at; dropped columns for 80%+ null values.

K4Q37, SPCSERVMO: Indicates age child started special services at, dropped for 80%+ null values4

LIVEUSA_YR, LIVEUSA_MO: Indicates how long the child has lived in the usa, dropped for 90%+ nulls

K11Q43R: Indicates how many times the child moved to a new address, imputed with median.

A1_AGE, A1_LIVEUSA, A2_AGE, A2_LIVEUSA, A1_DEPLSTAT, A2_DEPLSTAT, A1_SEX, A1_BORN, A1_EMPLOYED, A1_GRADE, A1_MARITAL, A1_RELATION, A2_SEX, A2_BORN, A2_EMPLOYED, A2_GRADE, A2_MARITAL, A2_RELATION, A1_ACTIVE, A2_ACTIVE, A1_PHYSHEALTH, A1_MENTHEALTH, A2_PHYSHEALTH, A2_MENTHEALTH, A1_GRADE_IF: Indicates details about the adults the child lives with. Dropped for lack of relevance.

HHCOUNT, HHCOUNT_IF, FAMCOUNT: Number of people living within a home, and details about those people. Dropped for lack of relevance.

BREATHING, SWALLOWING, STOMACH, PHYSICALPAIN, HANDS, COORDINATION, TOOTHACHES, GUMBLEED, CAVITIES, MEMORYCOND, WALKSTAIRS, DRESSING, ERRANDALONE, K2Q43B, BLINDNESS, ALLERGIES, ALLERGIES_CURR,ARTHRITIS, ARTHRITIS_CURR, K2Q40A, K2Q40B, K2Q61A, K2Q61B, K2Q41A, K2Q41B, K2Q42A, K2Q42B, HEART, HEART_BORN, HEART_CURR, HEADACHE, HEADACHE_CURR, K2Q38A, K2Q38B, K2Q33A, K2Q33B, K2Q32A, K2Q32B, DOWNSYN, BLOOD, SICKLECELL, THALASSEMIA, BLOOD_OTHER, BLOOD_SCREEN, CYSTFIB, CYSTFIB_SCREEN, GENETIC, GENETIC_SCREEN, K2Q34A, K2Q34B, K2Q36A, K2Q36B, K2Q60A, K2Q60B, K2Q37A, K2Q37B, K2Q30A, K2Q30B, K2Q31A, K2Q31B, K2Q31D, ADDTREAT, CONCUSSION, SEEKCARE, CONFIRMINJURY, K2Q05, OVERWEIGHT, K4Q23: Medical condition indicators; boolean columns imputed with no.

K6Q40: Question indicating if the child was ever breastfed, dropped since not applicable to older children.

S4Q01: Indicator that the child has been to a doctor in the past 12 months. Boolean column imputed with yes (few enough nulls to assume those children have been to a doctor

DOCPRIVATE: Indicates if the child has spoken privately to their doctor. Dropped since it's not applicable to children under 15

K6Q10: Indicates if doctor has asked adult if they're concerned about the child's development. Dropped since not applicable to older children

K4Q01, USUALGO, USUALSICK: Indicators about a place the child will usually go when sick. Boolean columns imputed with no

K4Q31_R: Indicators of the child's most recent eye exam, or that the child hasn't had a recent eye exam.

ALTHEALTH: Indicator that the child has had alternative healthcare; boolean column imputed with no

K4Q27: Indicator that the child needed healthcare they didn't receive, boolean column imputed with no

NOTELIG, AVAILABLE, APPOINTMENT, TRANSPORTCC, NOTOPEN, ISSUECOST: Reason child didn't receive needed healthcare, boolean columns imputed with no

HOSPITALSTAY: Indicator the child stayed overnight at a hospital in the past 12 months, boolean imputed with no

K6Q15, SESCURRSVC: Indicates the child has a special ed plan, boolean column imputed with no

K4Q36, K4Q38: Indicates the child revceived special services, boolean column imputed with no

K5Q10: Indicates the child needed a referral to see a doctor.

DECISIONS: Indicates healthcare decisions needed to be made about the child; null if child hasn't seen a doctor; boolean column imputed with no

K5Q21: Indicates if the guardian feels they could use extra help coordinating the child's care. Dropped for over 50% nulls

TREATCHILD: Indicates if child's doctor only treats children, dropped for over 50% null values

TREATADULT: Indicates if child's doctor has talked to adult about when the child will need to see a doctor who only treats adults. Dropped for over 60% nulls

MEDHISTORY: Indicates whether parent and child received child's medical history; dropped for over 50% nulls

WRITEPLAN: Indicates whether doctor worked with child and parent to create plan of care. Dropped for over 50% nulls

HEALTHKNOW: Indicates if parent knows how child will be insured in adulthood; dropped for over 50% nulls

CURRCOV: Indicates if child is covered by insurance. Boolean col imputed with yes

K12Q03, K12Q04, K12Q12, TRICARE, K11Q03R, HCCOVOTH: indicator cols for type of health insurance; booleans imputed with no

K3Q25: Indicates if the parent has struggles to pay for the child's healthcare. Boolean column imputed with no

STOPWORK, CUTHOURS, AVOIDCHG: Indicates if the parent has reduced amount worked or avoided changing jobs due to the child's health conditions. Dropped for lack of relevance.

REPEATED: Indicates if the child has repeated any grades, boolean col imputed with no

K7Q30, K7Q31, K7Q32, K7Q37, K7Q38: Indicates if the child has participated in specifc extracurricular activities in the past 12 months; boolean column imputed with no

BORNUSA: Indicates if the child was born in the USA; boolean column imputed with yes

K8Q35, EMOSUPSPO, EMOSUPFAM, EMOSUPHCP, EMOSUPWOR, EMOSUPADV, EMOSUPPEER, EMOSUPMHP, EMOSUPOTH: Indicates if the parent had someone to turn to for emotional support in raising the child; dropped for lack of relevance

K9Q40: Indicates if someone in the household smokes; boolean column imputed with mode

K11Q60, K11Q61, K11Q62, S9Q34: Indicates if someone in the family received government assistance; imputed with mode

K10Q11, K10Q12, K10Q13, K10Q14, K10Q20, K10Q22, K10Q23: Indicates details about the child's neighborhood; boolean columns imputed with mode

K9Q96: Indicates if the child has an adult they can rely on outside of the household; imputed with mode

ACE1, ACE3, ACE4, ACE5, ACE6, ACE7, ACE8, ACE9, ACE10, ACE12: Indicates childhood experiences; imputed with no

K2Q01, K2Q01_D: Indicates child's general health. Categorical col imputed with median

K5Q40, K5Q41, K5Q42: Questions about how the child's doctor treats the child and family; imputed with median and added imputation flag; col is null when child hasn't seen a doctor in the past 12 months, but imputing with a constant of 4 would too heavily scew our data toward indicating poor doctors.

K3Q20, K3Q22, K3Q21B: Columns asking about the child's health insurance; CURRCOV serves as a null flag for these columns and otherwise they aren't relevant.

K3Q22: Asks how often healthcare costs for the child are reasonable; dropped for over 25% nulls in addition to being very subjective and difficult to quantify

HOWMUCH: Indicates how much money the parent pays for the child's healthcare. Imputed with median

K7Q84_R, K7Q85_R, K7Q82_R, K7Q83_R, K7Q70_R: Questions about the child's behavior; some null when child is 5 or younger. Imputed with constant 5 (value not in question in place of a null flag

BULLIED_R, BULLY: Indicates how often the child has bullied/been bullied in the past 12 months; imputed with mode of 1 (indicating child is not bullied; which is likely to be accurate since most nulls come from the formtype T1 not having the question)

TALKABOUT, WKTOSOLVE, STRENGTHS, HOPEFUL: Indicates ways the family handles problems; imputed with median

K10Q30, K10Q31, K10Q40_R, GOFORHELP, K10Q41_R: Indicates factors about the child's neighborhood/community; imputed with median

K8Q31, K8Q32, K8Q34: Indicates parent's feelings about raising the child; imputed with median

ATHOMEHC, ARRANGEHC: Indicates details about health care the child receives; imputed with median

K7Q02R_R: Indicates how many days of school the child missed because of illness or injury; dropped for lack of relevance and moderate null count

K7Q04R_R: Indicates how many times the child's school contacted the adult; turned into boolean col, imputed with none

PHYSACTIV: Indicates how many days the child performed physical activities; dropped for moderate null count and lack of relevance

HOURSLEEP, HOURSLEEP05: Indicates how many hours of sleep the child got on average; divided by age of child; dropped but could be engineered into one column later.

SCREENTIME: Indicates how long the child was in front of a screen per week; imputed with median

K8Q11: Indicates how often the family eats meals together; imputed with median

FOODSIT: Indicates food situation of family; imputed with median

HCABILITY: Indicates if health has impacted child's ability to do things other children their age can do; imputed with median

K4Q20R, DOCROOM: Indicates details of the last visit to the child's doctor; dropped due to redundance with S4Q01

WGTCONC: Indicates if the parent is concerned about the child's weight; turned into boolean column, imputed with no

K4Q02_R: Indicates where child usually goes when sick, dropped for redundancy with K4Q01

DENTISTVISIT: Indicates if child has had a preventative dental visit; dropped for reduncancy with K4Q30_R

K4Q22_R: Indicates if child has seen a mental health professional; turned into a boolean and imputed with no

K4Q24_R: Indicates if child has seen a specialist other than a mental health specialist; turned boolean and imputed with no

HOSPITALER: Indicates if child has been to an ER in the past 12 months; turned boolean and imputed with no

K4Q04_R: Indicates if child has a personal doctor, turned boolean and imputed with no

K5Q20_R: Indicates if parent had help coordinating healthcare for child; dropped for redundancy with other col

K5Q31_R: Indicates if child's doctor communicated with school/child care/special ed; turned boolean and imputed with no

K8Q21: Indicates parent's opinions on raising/interacting with the child; imputed with median for simplicity; can potenaitlly get smarter about it

FWC: Dropped for irrelevance.

FPL_I1, FPL_I2, FPL_I3, FPL_I4, FPL_I5, FPL_I6, FPL_IF: Family poverty ratio, dropped for irrelevance

BIRTH_YR_F: Birth year data quality flag; dropped for irrelevance (data was consistent enough to use)

BIRTHWT, BIRTHWT_L, BIRTHWT_VL: Indicators of if child had low birth weight; turned boolean and imputed with no

HIGRADE, HIGRADE_TVIS: Information about reported adults, dropped for lack of relevance

INSTYPE, INSGAP, CURRINS: Insurance information, dropped for redundancy

FAMILY_R: Family structure; imputed with mode

HOUSE_GEN: Parental nativity indication; dropped for lack of relevance

BIRTHWT_OZ_S: Birth weight; imputed with median

SC_SEX_IF, SC_HISPANIC_R_IF, SC_RACE_R_IF, TENURE_IF: Imputation flag for other cols; dropped for lack of relevance (very few were positive)

SC_RACER: Child race indicator; no preprocessing needed

TOTFEMALE, TOTMALE: Count of children in household by sex; dropped for lack of relevance

AGEPOS4: Birth order of child; dropped for lack of relevance

SC_AGE_LT10, SC_AGE_LT9, SC_AGE_LT6, SC_AGE_LT4: Age for very young children; dropped for lack of relevance

SC_K2Q22, SC_K2Q19, SC_K2Q13, SC_K2Q10: Indicators of the child's development/treatments; boolean imputed with no

SC_ENGLISH: Indicates how well the child speaks english; imputed with median

SC_CSHCN: Indicates child's special health care needs status; no preprocessing needed

SC_HISPANIC_R: Indicates if child is hispanic; no preprocessing needed

SC_RACE_R: Race indicator; no preprocessing needed

TOTNONSHCN, TOTCSHCN, TOTAGE_12_17, TOTAGE_6_11, TOTAGE_0_5: Indicates details about children in household, dropped for lack of relevance

MPC_YN, METRO_YN: Indicates metropolitan status details; dropped for lack of relevance and moderate null count

YEAR: Indicates survey year, dropped for only having 1 value

MENBEVCOV: Indicates mental health coverage, imputed with median and added imputation flag

K4Q30_R: Indicates if the child has seen a dentist, boolean imputed with no

MAKEFRIEND: Indicates if child has trouble making friends, imputed with median

K3Q04_R: Indicates insurance, dropped for redundancy

BEDTIME: Indicates how often the child goes to bed at the same time every night; imputed with median

K7Q33: Indicates how often parent attended activities child participated in, imputed with median

 
K2Q35A_1_YEARS',K6Q41R_STILL',K6Q42R_NEVER',K6Q43R_NEVER',K6Q13A',K6Q13B',K6Q14A',K6Q14B',K4Q28X01',K4Q28X02',K4Q28X03',K4Q28X_EAR',K4Q28X04',K4Q28X05',SESPLANYR',SESPLANMO',K4Q37',SPCSERVMO',LIVEUSA_YR',LIVEUSA_MO',A1_LIVEUSA',A2_LIVEUSA',HANDS,COORDINATION',ALLERGIES_CURR',ARTHRITIS_CURR',K2Q40B',K2Q61B',K2Q41B',K2Q42B',HEART_BORN',HEART_CURR',HEADACHE_CURR',K2Q38B',K2Q33B',K2Q32B',SICKLECELL',THALASSEMIA',BLOOD_OTHER',BLOOD_SCREEN',CYSTFIB_SCREEN',GENETIC_SCREEN',K2Q34B',K2Q36B',K2Q60B',K2Q37B',K2Q30B',K2Q35B',AUTISMMED',AUTISMTREAT',K2Q31B',K2Q31D',ADDTREAT',SEEKCARE',CONFIRMINJURY',K6Q40',DOCPRIVATE',K6Q10',K6Q12',NOTELIG',AVAILABLE',APPOINTMENT',TRANSPORTCC',NOTOPEN',ISSUECOST',SESCURRSVC',K4Q38',TREATADULT',RECEIVECOPY',KEEPINSADULT',K12Q01_A',K12Q01_B',K12Q01_C',K12Q01_D',K12Q01_E',K12Q01_F',K12Q01_G',ONEWORD',TWOWORDS',THREEWORDS',ASKQUESTION',ASKQUESTION2,TELLSTORY',UNDERSTAND,DIRECTIONS',POINT',DIRECTIONS2',UNDERSTAND2',RHYMEWORD',K6Q20',K6Q27',K9Q41',A1_DEPLSTAT',A2_DEPLSTAT',ALLERGIES_DESC',ARTHRITIS_DESC',K2Q40C',CERPALS_DESC',K2Q41C',K2Q42C',HEART_DESC',HEADACHE_DESC',K2Q38C',K2Q33C',K2Q32C',BLOOD_DESC',GENETIC_DESC',K2Q34C',K2Q36C',K2Q60C',K2Q37C',K2Q30C',K2Q31C',DISCUSSOPT',RAISECONC', BESTFORCHILD', K6Q70_R', K6Q73_R', K6Q72_R', RECOGBEGIN', CLEAREXP',WRITENAME', RECSHAPES', DISTRACTED', WORKTOFIN', SIMPLEINST',PLAYWELL', NEWACTIVITY', HURTSAD', CALMDOWN', TEMPER', SITSTILL', RECOGABC', HOURSLEEP05', K6Q60_R', K6Q61_R', ', HCEXTENT', TREATNEED', K4Q26', K5Q11', K5Q22', K5Q32', COUNTTO', K6Q08_R', CONFIDENT', USEPENCIL', SLEEPPOS',COLOR', STARTSCHOOL', PLANNEEDS_R, SC_K2Q11, SC_K2Q12, SC_K2Q14, SC_K2Q15, SC_K2Q17, SC_K2Q18, SC_K2Q20, SC_K2Q21, SC_K2Q23, SC_RACEASIA, SC_RACEAIAN, BREASTFEDEND_DAY_S, BREASTFEDEND_WK_S, BREASTFEDEND_MO_S, FRSTFORMULA_DAY_S', FRSTFORMULA_WK_S', FRSTFORMULA_MO_S', FRSTSOLIDS_DAY_S, FRSTSOLIDS_WK_S, FRSTSOLIDS_MO_S: Dropped for having over 60% null values; not specificially examined.
