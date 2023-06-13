# CST383-Final-Murder-Prediction

## Introduction
The source data is from: https://www.murderdata.org/p/about.html. The objective is to figure out how the US government and law enforcement are being accountable for homicides, that were both solved and unsolved. We focused to know the data that is provided from the source from which weapons are being used and any distinguishing factors of the victims/offenders. We will be using the data to show any figures that show any possible regulations that can solve a possible homicide.

## Selection of Data

There are features and entries from the dataset but we've removed any empty and unnecessary like ID, Ori, Source, etc. We created a data frame that focused on two states to show a comparison of homicide data, the states are California and New Jersey.
The data that would be used have 6 numeric features and close to 20 categorical features. 
The features that would be used are VicAge, OffAge, Relationship, and others to find out about the weapons used in homicides and predict the actual murder weapons that were used.

Copied from MAP Data Dictionary, which can be downloaded here https://www.dropbox.com/s/lo6tgo8nnbpqeru/MAPdefinitionsSHR.pdf?dl=1 from the Murder Accountability Project website.

ID – Unique record identifier generated by MAP based on the report's YEAR, MONTH, INCIDENT, and ORI code. Alphanumeric 16-character format (A16).

CNTYFIPS – The Census Bureau’s Federal Information Processing Standards (FIPS) code designates the state and county of the reporting law enforcement agency. When using the SPSS format file (extension=.sav), the label name of the county is associated with a five-digit string variable. When using the Comma Separated Values format file (file extension=.csv) the original FIPS coding is replaced with the label indicating the county and state. (A15).

ORI – The alphanumeric variable describing the Originating Agency making the report. The first
two digits describe the state of the Originating Agency, the next three digits usually represent
the county in which the agency is located (according to an FBI numbering scheme) and the last
two digits describe the agency’s number within the state. (A7).

STATE – The alphanumeric variable describing the state of the Originating Agency making the
report. In most cases, the state was coded in a two-digit naming scheme. In the SPSS version of
the file, the full name of the state is associated as a label so that “AK” = “Alaska” or “AL” =
“Alabama.” (A6).

AGENCY – The alphanumeric variable describing the name of the law enforcement agency
making the report. (A450).

AGENTYPE – The one-digit numeric code describing the type of law enforcement agency making
the report so that 1=Sheriff, 2=County Police, 3=Municipality, 5=Primary State Law Enforcement
usually meaning the State Police, 6=Special Police, 7=Constable, 8=Tribal Police, 9=Regional
Police. When using the Comma Separated Values format file (file extension=.csv) the original
FBI numbering scheme is replaced with the alphanumeric label. (F1.0).

SOURCE – MAP-generated identifier if record provided by FBI (SOURCE=1) or was obtained by
MAP under the Freedom of Information Act from an Agency not participating in SHR reporting
to the FBI (SOURCE=0). Numeric single-digit format. (F1.0).

SOLVED – MAP-generated indicator of whether the Offender was identified at the time report was made
(SOLVED=1) or not identified (SOLVED=0). Numeric single-digit format. (F1.0).

YEAR – Year of homicide (or when the victim’s body was recovered.) Numeric four-digit. (F4.0).
STATENAME = Alphanumeric variable describing the original FBI naming and abbreviating
scheme for the state of the reporting agency. (A6).

MONTH – The month of homicide occurrence or when the victim’s body was recovered. So that
01=January and 02=February through 12=December. Numeric two-digit. (F2.0).

INCIDENT – A three-digit number describing the case number within the month in which a
homicide occurred. This does not necessarily correspond to the actual case number used in-house by police agencies. It is used to assist in building a unique record number for each case
and to differentiate each case reported within the same month. (F3.0).

ACTIONTYPE – A numeric variable describing the nature of the report received. Whether it was:
0=Normal Update or 1=Adjustment to a previous report. (F1.0).

HOMICIDE – An alphanumeric variable defining whether the report was “A” = “Murder or Nonnegligent manslaughter” or “B” = “Manslaughter by Negligence.” (A1).

SITUATION – An alphanumeric variable defining whether the crime had a single victim or
multiple victims and whether there was a single offender, multiple offenders or the number of
offenders was unknown. So that “A” = “Single Victim/Single Offender” and “B” = “Single
Victim/Unknown Offender” and so forth. (A1).

VICAGE – A three-digit numeric variable describing the age in years of the victim. To allow for
simpler mathematical calculations, MAP has changed the original alphanumeric coding of “NB”
for new born and “BB” for infant to a numeric value of zero to indicate the victim had not
achieved a full year of life. A value of 99, as in the original numbering scheme, represents all
victims 99 or older. A value of 999 represents victims whose age was not reported, usually
because the victim was unidentified and the age was unknown. (F3.0).

VICSEX – An alphanumeric variable representing whether the victim was “M” = ”Male” or “F” =
”Female” or “U” indicating “Unknown” gender, usually for conditions in which incomplete
remains were recovered. (A1).

VICRACE – An alphanumeric variable representing whether the victim was “A” = “Asian or
Pacific Islander” or “B” = “Black” or “I” = “American Indian or Alaskan Native” or “W” = “White”
or “U” victim was of “Unknown” race. (A1).

VICETHNIC – An alphanumeric variable representing whether the victim was “H” = “Hispanic
Origin” or “N” = “Not of Hispanic Origin” or “U” = “Unknown or Not Reported.” It should be
noted that many agencies decline reporting the ethnicity of victims and offenders. (A1).
OFFAGE – A three-digit numeric variable describing the age in years of the offender. When the
offender was not identified at the time of the report, age was reported as 999. A value of 99
represents all offenders 99 or older. (F3.0).

OFFSEX – An alphanumeric variable representing whether the offender was “M”=”Male” or
“F”=”Female” or “U” indicating “Unknown” gender, usually in conditions in which the offender
had not been identified at the time of the report. (A1).

OFFRACE – An alphanumeric variable representing whether the offender was “A” = “Asian or
Pacific Islander” or “B” = “Black” or “I” = “American Indian or Alaskan Native” or “W” = “White”
or “U” = “Unknown” race, usually in conditions in which the offender had not been identified at
the time of the report. (A1).

OFFETHNIC – An alphanumeric variable representing whether the offender was “H” = “Hispanic
Origin” or “N” = “Not of Hispanic Origin” or “U” = “Unknown or Not Reported.” It should be
noted that many agencies decline reporting the ethnicity of victims and offenders. (A1).

WEAPON – A two-digit numeric variable representing the weapon used in the crime. (F2.0).

Under this system, weapons are coded as:
11 = Firearm, type not stated
12 = Handgun – pistol, revolver, etc.
13 = Rifle
14 = Shotgun
15 = Other gun
20 = Knife or cutting instrument
30 = Blunt object – hammer, club, etc.
40 = Personal weapons, including beating
50 = Poison, does not include gas
55 = Pushed or thrown out of window
60 = Explosives
65 = Fire
70 = Narcotics or drugs, sleeping pills
75 = Drowning
80 = Strangulation or hanging
85 = Asphyxiation – includes death by gas
90 = Other or type unknown weapon

RELATIONSHIP – An alphanumeric variable describing the relationship between the victim and
the offender, if any. (A2). Under the original FBI criteria, relationship is coded as:
“AQ” = “Acquaintance”
“BF” = “Boyfriend”
“BR” = “Brother”
“CH” = “Common-law husband”
“CW” = “Common-law wife”
“DA” = “Daughter”
“EE” = “Employee”
“ER” = “Employer”
“FA” = “Father”
“FR” = “Friend”
“GF” = “Girlfriend”
“HO” = “Homosexual relationship”
“HU” = “Husband”
“IL” = “In-law”
“MO” = “Mother”
“NE” = “Neighbor”
“OF” = “Other family”
“OK” = “Other - known to victim”
“SD” = “Stepdaughter”
“SF” = “Stepfather”
“SI” = “Sister”
“SM” = “Stepmother”
“SO” = “Son”
“SS” = “Stepson”
“ST” = “Stranger”
“UN” = “Relationship not determined”
“WI” = “Wife”
“XH” = “Ex-husband”
“XW” = “Ex-wife”

CIRCUMSTANCES – A two-digit numeric variable representing the circumstances (or theory) for
the crime. (F2.0). The circumstances under the original FBI coding scheme are represented as:
2 = Rape
3 = Robbery
5 = Burglary
6 = Larceny
7 = Motor vehicle theft
9 = Arson
10 = Prostitution and commercialized vice
17 = Other sex offense
18 = Narcotic drug laws
19 = Gambling
26 = Other - not specified
32 = Abortion
40 = Lovers triangle
41 = Child killed by babysitter
42 = Brawl due to influence of alcohol
43 = Brawl due to influence of narcotics
44 = Argument over money or property
45 = Other arguments
46 = Gangland killings
47 = Juvenile gang killings
48 = Institutional killings
49 = Sniper attack
50 = Victim shot in hunting accident
51 = Gun-cleaning death - other than self
52 = Children playing with gun
53 = Other negligent handling of gun
59 = All other manslaughter by negligence
60 = Other
70 = All suspected felony type
80 = Felon killed by private citizen
81 = Felon killed by police
99 = Circumstances undetermined

SUBCIRCUM – A single-digit alphanumeric variable describing several conditions in which the
victim is reported to have been a criminal offender. (A2). Under the original FBI coding, these
conditions are described as:
“A” = “Felon attacked police officer”
“B” = “Felon attacked fellow police officer”
“C” = “Felon attacked a civilian”
“D” = “Felon attempted flight from a crime”
“E” = “Felon killed in commission of a crime”
“F” = “Felon resisted arrest”

VICCOUNT – The number of additional victims (not counting the victim included in the current
record) included in the Supplementary Homicide Report’s incident record, which can accept up
to 10 additional victims in a single incident report. (F3.0) Incidents of mass murder of more than
11 victims would require multiple SHR incident reports. The Murder Accountability Project’s
database captures all reported homicide victims as separate cases. Associated victims will have
identical ID numbers.

OFFCOUNT – The number of additional offenders (not counting the offender included in the
current record) included in the Supplementary Homicide Report’s incident record, which can
accept up to 10 additional offenders in a single incident report. (F3.0) Unlike victims, the
Murder Accountability Project does not create multiple case reports for additional offenders.
Only the first offender listed in the original SHR report is included.

FILEDATE – A six-digit alphanumeric variable describing the date a record was reported, not the
date of the occurrence of the crime. Note, in some cases, the date was not reported and has been
estimated. In some cases, the date indicates when local or state police provided the record to
MAP. A value of “030180” means the record was reported on March 1, 1980. (A6).

FSTATE – A two-digit alphanumeric variable representing the state in which a homicide was
reported. A value of “01” = “Alabama” and “02” = “Alaska” and so forth. (A2)

MSA – An eight-digit numeric variable representing the Census Bureau’s Federal Information
Processing Standards (FIPS) code for the Metropolitan Statistical Area from which a record was
reported. When using the Comma Separated Values format file (file extension=.csv) the original
FIPS coding is replaced with the label indicating the metropolitan area. (F8.0).

## Method

Tools:
- Numpy, Pandas, and Matplotlib for Data Analysis and Visualization
- Scikit-learn
- Google Collabs
- Anaconda Juppyter Notebook

  Methods:
  - Models: Linear Regression from Scikit-learn, KNeighborsClassifier, KNN
  - Features: We couldn't use the unknown information and also dropped Weapon and Relationship because they don't have numeric data.
 
 ## Results

 Data Visualization:
 
![project-graph1](https://github.com/ririve11/CST383-Final--Murder-Prediction/assets/136394215/545cd856-a0b0-47d6-99f5-91e8ffa3f3dd)
![project-graph2](https://github.com/ririve11/CST383-Final--Murder-Prediction/assets/136394215/4a97a71d-d265-4424-913d-ca0cb5ce7ce0)

Accuracy Tests:

![project-acc1](https://github.com/ririve11/CST383-Final--Murder-Prediction/assets/136394215/368a3656-61df-43dd-9d15-ae9919acc604)
![project-acc2](https://github.com/ririve11/CST383-Final--Murder-Prediction/assets/136394215/512d30ec-adae-4165-b67d-ddfa61863c3e)


Over the past decade, there has been a troubling upward trend in murder prediction data, specifically related to homicides involving gun violence and younger individuals in both California and New Jersey. This rise in violent crimes has raised significant concerns within these communities and across the nation. The data suggest that factors such as easy access to firearms, socioeconomic disparities, and involvement in criminal activities have contributed to this distressing phenomenon.

## Discussion

Based on the murder prediction dataset that includes information about the victim's age, gender, and race, as well as the offender's age, gender, and race, there is a hypothesis that analyzing these factors can provide valuable insights into unsolved homicides, including identifying patterns and correlations. By examining the characteristics of the victims and offenders, such as age, gender, and race, it may be possible to uncover potential motives, relationships, or patterns that can aid in the resolution of these cases. Additionally, considering the murder weapon in conjunction with these factors may further enhance the understanding of the crimes and potentially assist in narrowing down suspects or identifying common trends. This hypothesis assumes that a comprehensive analysis of these combined factors can offer a valuable avenue for uncovering crucial information and improving the investigation of unsolved homicides.

## Summary

The dataset containing information about the victim's details, offender's characteristics, murder weapons, and other factors plays a crucial role in finding answers to unsolved homicides in the country. By analyzing this dataset, patterns and correlations can be identified, leading to potential breakthroughs in investigations. The victim's information, including age, gender, and race, can provide insights into potential motives, relationships, or targeted demographics. Similarly, studying the offender's characteristics, such as age, gender, and race, can help in narrowing down potential suspects and identifying commonalities among perpetrators. The data on the weapons used in homicides is also valuable, as it can shed light on modus operandi and potential links between cases. Furthermore, considering other factors, such as geographic location, time of the crime, and any known circumstances, can further enhance the investigation process. By analyzing and synthesizing all these data points, investigators and law enforcement agencies can make informed decisions, develop new leads, and potentially solve unsolved homicides, providing closure and justice for the victims and their families.

## Video Link


 
