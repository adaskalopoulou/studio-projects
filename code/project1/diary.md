import pandas as pd
%matplotlib inline
df = pd.read_excel("publicspreadsheet.xlsx")
pd.set_option("display.max_columns", 100)
df.dtypes
df.shape

THE LARGEST:
popular = states_pp2.groupby('NAME')['PrimSource'].value_counts()
popular.groupby(level=0).nlargest(1)



SHIFT+ refresh = στο Network, inspector για να παρω το json


copy as curl
paste in terminal 
curl 'https:/....etc--compressed > output.json

output saved in the folder

SELENIUM documentation
http://selenium-python.readthedocs.io/locating-elements.html

plot
df_full.plot(x='Convicted', y='index1', kind='bar')

#DNA.loc[DNA['Last Name'] == 'Sutton']

----
PIE CHARTS

import matplotlib.pyplot as plt
 
# Data to plot
labels = 'Python', 'C++', 'Ruby', 'Java'
sizes = [215, 130, 245, 210]
colors = ['#437F7B', '#4F6289', '#CEAC6D', '#CE976D']
explode = (0.1, 0, 0, 0)  # explode 1st slice
 
# Plot
plt.pie(sizes, explode=explode, labels=labels, colors=colors,
        autopct='%1.1f%%', shadow=True, startangle=140)

plt.title('Cases received in DNA labs')
plt.axis('equal')
plt.show()


PALETE: http://paletton.com/#uid=73g0u0kf7pW5NGhaguWk5lhoUgn
-----

MAKE PIES BIGGER

import matplotlib.pyplot as plt
 
# Data to plot
labels = 'Mistaken Witness Identification', 'False or Misleading Forensic Evidence', 'Perjury or False Accusation', 'Official Misconduct'
sizes = [8, 9, 7, 7]
colors = ['#437F7B', '#4F6289', '#CEAC6D', '#CE976D']
explode = (0, 0, 0, 0)  # explode 1st slice
fig=plt.figure(figsize=(10,10)) 
ax=fig.add_subplot(1,1,1)
# Plot
ax.pie(sizes, explode=explode, labels=labels, colors=colors,
        autopct='%1.1f%%', shadow=True, startangle=140)
ax.set_title('Reason behind first conviction that lead to 2 DNA exonerations')
ax.axis('equal')
plt.show()

----

df = df.rename(columns={'oldName1': 'newName1', 'oldName2': 'newName2'})
# OR
df.rename(columns={'oldName1': 'newName1', 'oldName2': 'newName2'}, inplace=True)

------

BINS- group bars
https://chrisalbon.com/python/pandas_binning_data.html

bins = [13, 18, 22, 26, 30, 34, 38, 42, 46, 50, 54, 58, 62, 66]
group_names = ['14-18', '19-22', '23-26', '27-30', '31-34', '35-38', '39-42', '43-46', '47-50', '51-54', '55-58', '59-62', '63-66']
#includes the number on the right and not on the left
DNA['age_groups'] = pd.cut(df['Age'], bins, labels=group_names)
DNA['age_groups'].value_counts().sort_index().plot(kind='bar', figsize=(10,10), color ='#437F7B')

------




---

CURL TO JSON 

CHROME Inspect
- admin-ajax
- Copy
- Copy as curl

TERMINAL
curl (paste) --display the code in the terminal
curl (paste) > output.json   (saves it)

-----

links to readings:
http://dnapolicyinitiative.org/why-dna-is-not-enough/
https://www.cybgen.com/information/presentations/2017/AAFS/Perlin-Watson-Hampikian-When-DNA-alone-is-not-enough-exoneration-by-computer-interpretation/page.shtml
https://www.nytimes.com/2017/04/26/us/retro-hair-analysis.html?_r=0
http://www.sciencemag.org/news/2016/03/forensics-gone-wrong-when-dna-snares-innocent
https://www.forensicmag.com/article/2005/01/evolution-dna-evidence-crime-solving-judicial-and-legislative-history
https://www.fbi.gov/services/laboratory/biometric-analysis/dna-casework

----
links to datasets:

https://www.bjs.gov/index.cfm?ty=pbdetail&iid=1115
https://www.bjs.gov/index.cfm?ty=pbdetail&iid=1117
https://www.innocenceproject.org/all-cases/#exonerated-by-dna
https://www.law.umich.edu/special/exoneration/Pages/about.aspx
https://www.law.umich.edu/special/exoneration/Documents/Changes_In_DNA_Exonerations.pdf
https://www.law.umich.edu/special/exoneration/Pages/Exoneration-by-Year.aspx
https://www.law.umich.edu/special/exoneration/Pages/glossary.aspx
-----


headlines

DNA forensics in the era of errors
DNA forensics: trapped in its own success
The champion of forensic science in doubt
DNA forensics under the microscope
When DNA is wrong! 

-----

still need to explain:

"DNA evidence is so powerful because it has firm roots in science and is backed by statistics." 


BIOLOGY
mitochondrial DNA introduction to the processes

MIXTURE

CONTAMINATION

PROBABILITIES

- "random match probability", the chance that if you pick a person at random they would match this DNA sample.


SOCIAL IMPACT
age of victims, years lost, adolescence, Sutton's case

BENEFITS TO BE AKNOWLEDGED
- "cold case": take from police closets all kinds of objects, bloody shirt and test it for DNA

OTHER SCIENCE PROBLEMS:
Am I going to explore them? 
ex. hair analyis



-----------

datasets
https://www.law.umich.edu/special/exoneration/Pages/mission.aspx
https://www.bjs.gov/index.cfm?ty=pbdetail&iid=1115
https://www.innocenceproject.org/all-cases/#exonerated-by-dna

https://www.law.umich.edu/special/exoneration/Pages/Exoneration-by-Year.aspx
https://www.law.umich.edu/special/exoneration/Documents/Changes_In_DNA_Exonerations.pdf
http://dnapolicyinitiative.org/why-dna-is-not-enough/
https://www.cybgen.com/information/presentations/2017/AAFS/Perlin-Watson-Hampikian-When-DNA-alone-is-not-enough-exoneration-by-computer-interpretation/page.shtml
https://www.nytimes.com/2017/04/26/us/retro-hair-analysis.html?_r=0
http://www.sciencemag.org/news/2016/03/when-dna-snares-innocent

history
https://www.forensicmag.com/article/2005/01/evolution-dna-evidence-crime-solving-judicial-and-legislative-history

Tables...

1. 
sdna0108.wk1      
Table 8. Status of case workloads in DNA crime laboratories,  by type of case, 1999-2000.

sdna9810.WK1        
Table 10.  Status of case workloads in DNA laboratories, by type of case, 1996-97

2.
sdna0107.wk1      
Table 7. Type of agencies submitting DNA samples to laboratories for analyses, 2001.

sdna98h1.WK1        
Highlights figure 1.  Agencies from which DNA labs may receive samples to analyze

3.
sdna0106.wk1      
Table 6. Crime laboratories with full-time DNA staff, 2001.
sdna9807.WK1        
Table 7.  Number of full-time staff members for DNA laboratories, by type of position, 1998

4.
sdna0105.wk1      
Table 5. Standard guidelines DNA crime laboratories follow, 2001.
sdna98t1.WK1        
Text table 1.  DNA laboratory standard guidelines, 1998

5.
sdna0101.wk1      Table 1. Status of workloads in DNA crime laboratories,  by type of case, 1997-2000.
sdna9810.WK1        Table 10.  Status of case workloads in DNA laboratories, by type of case, 1996-97

6. 
sdna0102.wk1      Table 2. Analytical responsibilities of crime laboratories which perform DNA analysis, 2001.
sdna9801.WK1        Table 1.  Forensic crime laboratory responsibilities, 1998
