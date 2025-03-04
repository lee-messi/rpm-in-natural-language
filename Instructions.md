﻿# Instructions for Reproducing Analyses
**Last Updated: 2 Oct 2023**

Any difficulties reproducing the analysis, please contact the corresponding author, [Messi H.J. Lee](mailto:hojunlee@wustl.edu). 


## Guide to the Repository Folders (in Alphabetical Order)

- Attribute Word Stimuli
   - Code used to check if word is projected in the word embedding model (**exist.py**)
   - Code used to list words sharing highest cosine similarity values with a term (**query.py**)
   - Folder containing attribute word stimuli as .csv files (**Word Stimuli**)

* Corpus 
   * Code used to merge raw COCA files (**merge.py**)
   * Code used to pre-process merged COCA (**preprocess.py**)

- Embedding Model
   - Code used to convert embedding model into .txt format (**convert_to_txt.py**)
   - Code used to train the word embedding model (**train.py**)

* Exploratory Analyses
   * Code used to calculate the correlation between scores (**correlation.py**)
   * Code used to look for occurrences of expressions in COCA (**search_coca.py**)
   * Code used to count the number of times an expression occurs in COCA (**word_count.py**)

- Group Word Stimuli 
   - Three folders each containing code used to select group word stimuli, code used to filter words that are projected in the word embedding model, and group word stimuli as .csv files (**Names60**, **Names70**, **Names7020**)
   - 2010 Census data of common surnames in the United States of America (**surnames_2010.csv**)

* Meta Analysis 
   * ALC embeddings of group and attribute words for each text category (**alc_embeddings.RData**)
   * Code used to perform meta analysis of WEAT *D* scores (**alc_meta_analysis.R**)
   * Code used to perform meta regressions of WEAT *D* scores (**alc_meta_regression.R**)
   * Code used to perform WEATs within individual text categories (**alc_meta_weat.R**)
   * Code used to plot meta-analysis results (**meta_plot.R**)
   * Folder containing the plots of meta-analysis results (**Plots**)
   * Code used to induce ALC embeddings for each text category (**prep_alc_embeddings.R**)
   * Code used to save COCA and the word embedding model as an .RData file (**prep_meta.R**)
   * Folder containing results of WEATs within individual text categories and the meta-analytic esitmates (**Results**)

- SC-WEAT
   - Code used to plot SC-WEAT results (**plot_scweat.R**)
   - Code used to perform SC-WEATs (**scweat.py**)
   - Folder containing the plot of SC-WEAT *D*s (**Plots**)
   - Folder containing the results of SC-WEATs (**Results**)

* Supplement. Domain Analysis
   * Four folders each containing domain-specific attribute word stimuli as .csv files, results of WEATs as .csv files, and code used to perform WEATs (**intellectual_mental**, **legal_status**, **moral**, **social_cultural**)

- Supplement. Alternative Foreignness Word Stimuli
   - Folder containing Americanness word stimuli and alternative foreignness word stimuli as .csv files (**Attribute Word Stimuli**)
   - Code used to perform WEATs using alternative foreignness word stimuli (**foreignness_weat.py**)
   - Folder containing the results of WEATs (**Results**)
   
* Supplement. Meta Analysis
   * ALC embeddings of group words for each text category and COCA embeddings of attribute words (**alc_embeddings.RData**)
   * Code used to perform meta analysis of WEAT *D* scores (**alc_meta_analysis.R**)
   * Code used to perform meta regressions of WEAT *D* scores (**alc_meta_regression.R**)
   * Code used to perform WEATs within individual text categories (**alc_meta_weat.R**)
   * Code used to plot meta-analysis results (**meta_plot.R**)
   * Folder containing the plots of meta-analysis results (**Plots**)
   * Code used to append ALC embeddings of group words and the COCA embeddings of attribute words as lists (**prep_alc_embeddings.R**)
   * Folder containing results of WEATs within individual text categories and the meta-analytic esitmates (**Results**)

- Supplement. RIPA
   - Code used to plot RIPA results (**plot_ripa.R**)
   - Folder containing the plot of RIPA effect sizes (**Plots**)
   - Folder containing RIPA effect sizes (**Results**)
   - Code used to compare RIPA scores (**ripa.py**)

* WEAT
   * Code used to plot WEAT results (**plot_weat.R**)
   * Folder containing the plot of WEAT *D*s (**Plots**)
   * Folder containing the results of WEATs (**Results**)
   * Code used to perform WEATs (**weat.py**)

## Data Availability Statement

This GitHub repository does not include the following files: 
- The word embedding model trained on COCA because of its size. You can access it on our [OSF repository](https://osf.io/n5xyk/?view_only=ffd4adcfedb84deda7282ccf19bc3aac). 
* All files containing the Corpus of Contemporary American English (COCA) because the corpus is proprietary and access to the corpus must be purchased separately on [their website](https://www.english-corpora.org/coca/).

## What would you like to do?
* **Q: Interested in reproducing analyses with access to COCA?** 
   * A: Follow the below work flow from top to bottom. 

- **Q: Interested in reproducing analyses without access to COCA?** 
   - A: We have made it so that you can reproduce the analyses without access to COCA. Follow the below work flow from top to bottom skipping those steps that start with *With Access to COCA*. 

## Before You Begin: Install the following packages
* Python Packages (Python version used: 3.11.4). If Python 3 is not installed, download [a version of Python 3](https://www.python.org/downloads/).
   * numpy: https://pypi.org/project/numpy/
   * pandas: https://pypi.org/project/pandas/
   * nltk: https://pypi.org/project/nltk/
   * mapply: https://pypi.org/project/mapply/
   * contractions: https://pypi.org/project/contractions/
   * tqdm: https://pypi.org/project/tqdm/
   * gensim: https://pypi.org/project/gensim/

- R Packages (R version used: 4.2.2). If R is not installed, download [a version of R](https://cran.r-project.org/).
   - tidyverse: https://cran.r-project.org/web/packages/tidyverse/index.html
   - ggplot2: https://cran.r-project.org/web/packages/ggplot2/index.html
   - ggpubr: https://cran.r-project.org/web/packages/ggpubr/index.html
   - ggsci: https://cran.r-project.org/web/packages/ggsci/index.html
   - reticulate: https://cran.r-project.org/web/packages/reticulate/index.html
   - conText: https://cran.r-project.org/web/packages/conText/index.html
   - quanteda: https://cran.r-project.org/web/packages/quanteda/index.html
   - text2vec: https://cran.r-project.org/web/packages/text2vec/index.html
   - corpus: https://cran.r-project.org/web/packages/corpus/index.html
   - meta: https://cran.r-project.org/web/packages/meta/index.html

## Workflow for Reproducing Analyses in the Main Text

### *With Access to COCA:* Prepare the Word Embedding Model (Corpus Folder)
#### **Merge Corpus of Contemporary American English (COCA)**
* Store all raw COCA files (in .txt format) inside the "Raw” subfolder of the "Corpus” folder.
* Execute “merge.py” inside the “Corpus” folder. 
   - Run “python3 merge.py” in Terminal or the Command Line.
   - This code merges all .txt files of COCA and saves it as *merged\_coca.pkl* in the “Corpus” folder.
- ***Note: As *merged\_coca.pkl* contains the entirety of COCA, it is not provided as part of this repository.***


#### **Pre-process COCA**
* Confirm that *merged\_coca.pkl* is inside the “Corpus” folder.
* Execute “preprocess.py” inside the “Corpus” folder. 
   - Run “python3 preprocess.py” in Terminal or the Command Line. 
   - This code preprocesses COCA and saves it as *preprocessed\_coca.pkl* and *cleaned\_coca.pkl* in the “Corpus” folder. *preprocessed\_coca.pkl* is the version used for training the word embedding model. 
- ***Note: As both *preprocessed\_coca.pkl* and *cleaned\_coca.pkl* contain the entirety of COCA, they are not provided as part of this repository.***


#### **Train the word embedding model**
* Confirm that *preprocessed\_coca.pkl* is inside the “Corpus” folder.
* Execute “train.py” inside the "Embedding Model” folder.  
   - Run “python3 train.py” in Terminal or the Command Line. 
   - This code trains a word embedding model and saves it as *coca.model*, *coca.model.syn1neg.npy*, and *coca.model.wv.vectors.npy* in the "Embedding Model” folder. 


#### **Convert the word embedding model into .txt format**
* Confirm that *coca.model*, *coca.model.syn1neg.npy*, and *coca.model.wv.vectors.npy* are all inside the "Embedding Model” folder. 
* Execute “convert\_to\_txt.py” inside the "Embedding Model” folder. 
   - Run “python3 convert\_to\_txt.py” in Terminal or the Command Line. 
   - This code converts the trained word embedding model into .txt format and saves it as *coca.txt* in the "Embedding Model" folder. 


### **Select Group World Stimuli (Group Word Stimuli Folder)**
#### Group word stimuli using the 70% threshold
* Confirm that *surnames\_2010.csv* and the "Names70" subfolder are inside the "Group Word Stimuli" folder
* Execute “surname\_selection\_70.R” inside the “Names70" subfolder of the “Group Word Stimuli" folder. 
   - Run “Rscript surname\_selection\_70.R” in Terminal or the Command Line. 
   - This code saves 80 names that can be used to represent racial/ethnic groups and saves them as *black\_names.csv*, *asian\_names.csv*, *hispanic\_names.csv*, and *white\_names.csv* in the “Names70" subfolder of the "Group Word Stimuli” folder.
* Manually inspect the generated .csv files for names that should be connected by hyphens (e.g. Jean-Baptiste). Place an underscore where the hyphen should be located for those names. 
* Execute “exist\_70.py” inside the “Names70” subfolder of the "Group Word Stimuli” folder.
   - Run “python3 exist\_70.py” in Terminal or the Command Line.
   - This code filters the names inside *black\_names.csv*, *asian\_names.csv*, *hispanic\_names.csv*, and *white\_names.csv* that have projections in the trained word embedding model.
* Manually inspect the .csv files for names that are frequently used in contexts other than names. Remove those names. Retain the top fifty names.
   - The removed names can be found in the Supplemental Materials.


#### Group word stimuli using the 60% threshold
* Confirm that *surnames\_2010.csv* and the "Names60" subfolder are inside the "Group Word Stimuli" folder
* Execute “surname\_selection\_60.R” inside the “Names60" subfolder of the “Group Word Stimuli" folder. 
   - Run “Rscript surname\_selection\_60.R” in Terminal or the Command Line. 
   - This code saves 80 names that can be used to represent racial/ethnic groups and saves them as *black\_names.csv*, *asian\_names.csv*, *hispanic\_names.csv*, and *white\_names.csv* in the “Names60" subfolder of the "Group Word Stimuli” folder.
* Manually inspect the generated .csv files for names that should be connected by hyphens (e.g. Jean-Baptiste). Place an underscore where the hyphen should be located for those names. 
* Execute “exist\_60.py” inside the “Names60” subfolder of the "Group Word Stimuli” folder.
   - Run “python3 exist\_60.py” in Terminal or the Command Line.
   - This code filters the names inside *black\_names.csv*, *asian\_names.csv*, *hispanic\_names.csv*, and *white\_names.csv* that have projections in the trained word embedding model. 
* Manually inspect the .csv files for names that are frequently used in contexts other than names. Remove those names. Retain the top fifty names.
   - The removed names can be found in the Supplemental Materials.


#### Group word stimuli using the 70% + 20% threshold
* Confirm that *surnames\_2010.csv* and the "Names7020" subfolder are inside the "Group Word Stimuli" folder
* Execute “surname\_selection\_7020.R” inside the “Names7020" subfolder of the “Group Word Stimuli" folder. 
   - Run “Rscript surname\_selection\_7020.R” in Terminal or the Command Line. 
   - This code saves 80 names that can be used to represent racial/ethnic groups and saves them as *black\_names.csv*, *asian\_names.csv*, *hispanic\_names.csv*, and *white\_names.csv* in the “Names7020" subfolder of the "Group Word Stimuli” folder.
* Manually inspect the generated .csv files for names that should be connected by hyphens (e.g. Jean-Baptiste). Place an underscore where the hyphen should be located for those names. 
* Execute “exist\_7020.py” inside the “Names7020” subfolder of the "Group Word Stimuli” folder.
   - Run “python3 exist\_7020.py” in Terminal or the Command Line.
   - This code filters the names inside *black\_names.csv*, *asian\_names.csv*, *hispanic\_names.csv*, and *white\_names.csv* that have projections in the trained word embedding model. 
* Manually inspect the .csv files for names that are frequently used in contexts other than names. Remove those names. Retain the top fifty names.
   - The removed names can be found in the Supplemental Materials.


### **Select Attribute Word Stimuli (Attribute Word Stimuli Folder)**
* Confirm that *superior\_primary.csv*, *inferior\_primary.csv*, *american\_primary.csv*, and *foreign\_primary.csv* are inside the “Word Stimuli” subfolder of the "Attribute Word Stimuli” folder. These words can be found as bolded words in Tables 2 and 3 of the Main Text. 
* Create duplicates of the primary word lists and name them *superior.csv*, *inferior.csv*, *american.csv*, and *foreign.csv*.
* Execute “query.py” inside the “Attribute Word Stimuli" folder. 
   - Run “python3 query.py” followed by the primary word of interest in Terminal or the Command Line (e.g. Run “python3 query.py capable” for the word “capable”).
   - This code prints the words sharing the highest cosine similarity values with the primary word of interest in descending order of cosine similarity. 
   - Using the output, manually select two words that share meaning ***and*** high cosine similarity values with the primary word. Append the two words to *superior.csv*, *inferior.csv*, *american.csv*, and *foreign.csv*.  

- ***Note: Words sharing high cosine similarity values with the primary word may not always be analogous in meaning with the primary word. For instance, the words sharing the highest cosine similarity value with “capable” were “not\_capable” and “incapable”. This is why it is important to select words that share both meaning and high cosine similarity values with the primary word.***


### **Word Embedding Association Tests (WEAT Folder)**
#### Perform Word Embedding Association Tests
* Confirm that *black\_names.csv*, *asian\_names.csv*, *hispanic\_names.csv*, and *white\_names.csv* are inside the “Names70", "Names60", and "Names7020" subfolders of the “Group Word Stimuli" folder, that *superior.csv*, *inferior.csv*, *american.csv*, and *foreign.csv* are inside the “Word Stimuli" subfolder of the “Attribute Word Stimuli" folder, and that *coca.model*, *coca.model.syn1neg.npy*, and *coca.model.wv.vectors.npy* are inside the "Embedding Model” folder. 
* Execute “weat.py” inside the "WEAT” folder. 
   - Create a “Results” subfolder inside the “WEAT" folder. 
   - Run “python3 weat.py” in Terminal or the Command Line. 
   - This code computes the WEAT *D*s and their 95% confidence intervals for all group comparisons and saves them as a .csv file in the “Results” subfolder of the "WEAT” folder. Modify lines 118 - 120 and lines 212 - 214 so that the lines correspond to the threshold value used to compile the group word stimuli. 


#### Visualize WEAT results
* Confirm that *weat\_results\_70.csv*, *weat\_results\_60.csv*, and *weat\_results\_7020.csv* are inside the “Results” subfolder of the “WEAT" folder. 
* Execute “plot\_weat.R” inside the "WEAT” folder. 
   - Create a “Plots" subfolder inside the “WEAT" folder. 
   - Run “Rscript plot\_weat.R” in Terminal or the Command Line. 
   - This code visualizes superiority and Americanness WEAT *D* scores and their 95% confidence intervals as a single plot and saves it in the “Plots" subfolder of the “WEAT" folder. Modify lines 19 - 21 and lines 83 - 85 so that they correspond to the threshold value used to compile the group word stimuli.


### **Single-Category Word Embedding Association Tests (SC-WEAT Folder)**
#### Perform Single-Category Word Embedding Association Tests
* Confirm that *black\_names.csv*, *asian\_names.csv*, *hispanic\_names.csv*, and *white\_names.csv* are inside the "Names70" subfolder of the “Group Word Stimuli" folder and that *superior.csv*, *inferior.csv*, *american.csv*, and *foreign.csv* are inside the “Word Stimuli" subfolder of the “Attribute Word Stimuli" folder.
* Execute “scweat.py” inside the "SC-WEAT" folder. 
   - Create a “Results” subfolder inside the “SC-WEAT" folder. 
   - Run “python3 scweat.py” in Terminal or the Command Line. 
   - This code computes the Superiority and Americanness SC-WEAT *D*s and their 95% confidence intervals for all groups and saves them as *scweat_results.csv* in the “Results” subfolder of the "SC-WEAT” folder. 


#### Visualize SC-WEAT results
* Confirm that *scweat\_results.csv* is inside the “Results” subfolder of the “SC-WEAT" folder. 
* Execute “plot\_scweat.R” inside the SC-WEAT” folder. 
   - Create a “Plots" subfolder inside the “SC-WEAT" folder. 
   - Run “Rscript plot\_scweat.R” in Terminal or the Command Line. 
   - This code visualizes the superiority and Americanness SC-WEAT *D*s and their 95% confidence intervals on a two-dimensional plane and saves it as *scweat2d\_plot.pdf* in the "Plots” subfolder of the “SC-WEAT" folder. 


### **Meta-Analysis and Meta-Regression of WEAT *D*s (Meta Analysis Folder)**
#### *With Access to COCA:* Prepare an .RData file for easy loading objects
* Confirm that *cleaned\_coca.pkl* is inside the “Corpus” folder and that *coca.txt* is inside the “Embedding Model" folder. 
* Execute “prep\_meta.R” inside the “Meta Analysis” folder.
   - Run “Rscript prep\_meta.R” in Terminal or the Command Line. 
   - This code loads the preprocessed version of COCA and the trained word embedding model and saves them as *meta.RData*. 
- ***Note: As “meta.RData” contains the entirety of COCA, it is not provided as part of this repository.***


#### *With Access to COCA:* Induce ALC embeddings
* Confirm that *meta.RData* is inside the “Meta Analysis" folder, that *black\_names.csv*, *asian\_names.csv*, *hispanic\_names.csv*, and *white\_names.csv* are inside the “Names70" subfolder of the "Group Word Stimuli” folder, and that *superior.csv*, *inferior.csv*, *american.csv*, and *foreign.csv* are inside the “Word Stimuli" subfolder of the “Attribute Word Stimuli" folder.
* Execute “prep_alc_embeddings.R” inside the "Meta Analysis” folder. 
   - Run “Rscript prep\_alc\_embeddings.R” in Terminal or the Command Line. 
   - This code induces ALC embeddings of both group and attribute words for each individual text categories and saves them as *alc\_embeddings.RData* in the “Meta Analysis" folder. 


#### Perform WEATs using the induced ALC embeddings
* Confirm that *alc\_embeddings.RData* is inside the "Meta Analysis" folder.
* Execute “meta\_weat\_alc\_embeddings.R” inside “Meta Analysis” folder. 
   - Create a “Results” subfolder inside the “Meta Analysis" folder. 
   - Run “Rscript meta\_weat\_alc\_embeddings.R” in Terminal or the Command Line. 
   - This code uses the ALC embeddings induced for each text category to perform series of WEATs and saves the results as *acad\_weat\_results.csv*, *blog\_weat\_results.csv*, *fic\_weat\_results.csv*, *mag\_weat\_results.csv*, *news\_weat\_results.csv*, *spok\_weat\_results.csv*, *tvm\_weat\_results.csv*, and *web\_weat\_results.csv* in the "Results" subfolder of the "Meta Analysis” folder.


#### Perform Random-effects meta-analysis
* Confirm that *acad\_weat\_results.csv*, *blog\_weat\_results.csv*, *fic\_weat\_results.csv*, *mag\_weat\_results.csv*, *news\_weat\_results.csv*, *spok\_weat\_results.csv*, *tvm\_weat\_results.csv*, and *web\_weat\_results.csv* are inside the “Results” subfolder of the “Meta Analysis” folder. 
* Execute “meta\_analysis.R” inside the “Meta Analysis” folder. 
   - Confirm that "Results" subfolder is inside the "Meta Analysis" folder. 
   - Run “Rscript alc\_meta\_analysis.R” in Terminal or the Command Line. 
   - This code performs random-effects meta analyses across text categories and saves the meta-analytic estimates and their 95% confidence intervals as *superior\_meta\_estimate.csv* and *american\_meta\_estimate.csv* in the “Results" subfolder of the “Meta Analysis" folder. This code also calculates meta-analytic estimates across group comparisons and the overall meta-analytic estimates for each stereotype dimension. 


#### Visualize meta-analysis results
* Confirm that *acad\_weat\_results.csv*, *blog\_weat\_results.csv*, *fic\_weat\_results.csv*, *mag\_weat\_results.csv*, *news\_weat\_results.csv*, *spok\_weat\_results.csv*, *tvm\_weat\_results.csv*, and *web\_weat\_results.csv* are inside the “Results” subfolder of the “Meta Analysis” folder. 
* Execute “meta\_plot.R” inside the "Meta Analysis" folder. 
   - Create a “Plots" subfolder inside the "Meta Analysis" folder. 
   - Run “Rscript meta\_plot.R” in Terminal or the Command Line. 
   - This code uses the WEAT *D*s and their 95% confidence intervals calculated using the ALC embeddings and the meta-analytic estimates calculated using random-effects meta analyses to visualize them in single plots (one for each dimension). The plots are saved as *superior\_meta.pdf* and *american\_meta.pdf* in the “Plots" subfolder of the "Meta Analysis" folder. 


#### Perform meta-regressions
* Confirm that *acad\_weat\_results.csv*, *blog\_weat\_results.csv*, *fic\_weat\_results.csv*, *mag\_weat\_results.csv*, *news\_weat\_results.csv*, *spok\_weat\_results.csv*, *tvm\_weat\_results.csv*, and *web\_weat\_results.csv* are inside the “Results” subfolder of the “Meta Analysis” folder. 
* Execute “alc\_meta\_regression.R” inside the "Meta Analysis" folder. 
   - Run “Rscript meta\_regression.R” in Terminal or the Command Line. 
   - This code performs meta-regressions comparing the WEAT *D*s of an individual text category with those of other categories. 


### **Exploratory Analyses (Exploratory Analyses Folder)**
#### Correlational Analysis
* Confirm that *black\_names.csv*, *asian\_names.csv*, and *hispanic\_names.csv* are inside the “Names70" subfolder of the "Group Word Stimuli” folder, that *superior.csv*, *inferior.csv*, *american.csv*, and *foreign.csv* are inside the “Word Stimuli” subfolder of the “Attribute Word Stimuli" folder, and that *coca.model* is inside the “Embedding Model" folder. 
* Execute "correlation.py” inside the "Exploratory Analyses” folder. 
   - Run “python3 correlation.py” in Terminal or the Command Line. 
   - This code calculates the correlation between the superiority and Americanness scores of African, Asian, and Hispanic peoples' group words. 

#### Count the frequency of word stimuli in COCA
* Confirm that *black\_names.csv*, *asian\_names.csv*, *hispanic\_names.csv*, and *white\_names.csv* are inside the “Names70" subfolder of the "Group Word Stimuli” folder, that *superior.csv*, *inferior.csv*, *american.csv*, and *foreign.csv* are inside the “Word Stimuli” subfolder of the “Attribute Word Stimuli" folder, and that *preprocessed\_coca.pkl* is inside the “Corpus" folder. 
* Execute “word_count.py” inside the "Exploratory Analyses” folder. 
   - Run “python3 word_count.py” in Terminal or the Command Line. 
   - This code counts the total number of times the group and attribute word stimuli occur inside COCA. 


## Workflow for reproducing analyses in the Supplemental Materials

### **Meta-analysis and Meta-Regressions of WEAT *D*s using ALC Embeddings of Group Words and COCA Embeddings of Attribute Words (Supplement. Meta Analysis Folder)**

#### Prepare ALC embeddings of group words and COCA embeddings of attribute words
* Confirm that *meta.RData* and *alc_embeddings.RData* are inside the “Meta Analysis" folder, that *superior.csv*, *inferior.csv*, *american.csv*, and *foreign.csv* are inside the “Word Stimuli" subfolder of the “Attribute Word Stimuli" folder.
* Execute “prep_alc_embeddings.R” inside the "Supplement. Meta Analysis” folder. 
   - Run “Rscript prep\_alc\_embeddings.R” in Terminal or the Command Line. 
   - This code appends ALC embeddings of group words and the COCA embeddings of attribute words as lists and saves them as *alc\_embeddings.RData* in the “Supplement. Meta Analysis" folder. 


#### Perform WEATs using ALC embeddings of group words and COCA embeddings of attribute words
* Confirm that *alc\_embeddings.RData* is inside the "Supplement. Meta Analysis" folder.
* Execute “meta\_weat\_alc\_embeddings.R” inside “Supplement. Meta Analysis” folder. 
   - Create a “Results” subfolder inside the “Supplement. Meta Analysis" folder. 
   - This code uses the ALC embeddings of group words and COCA embeddings of attribute words to perform series of WEATs and saves the results as *acad\_weat\_results.csv*, *blog\_weat\_results.csv*, *fic\_weat\_results.csv*, *mag\_weat\_results.csv*, *news\_weat\_results.csv*, *spok\_weat\_results.csv*, *tvm\_weat\_results.csv*, and *web\_weat\_results.csv* in the "Results" subfolder of the "Supplement. Meta Analysis” folder.


#### Perform Random-effects meta-analysis
* Confirm that *acad\_weat\_results.csv*, *blog\_weat\_results.csv*, *fic\_weat\_results.csv*, *mag\_weat\_results.csv*, *news\_weat\_results.csv*, *spok\_weat\_results.csv*, *tvm\_weat\_results.csv*, and *web\_weat\_results.csv* are inside the “Results” subfolder of the “Supplement. Meta Analysis” folder. 
* Execute “meta\_analysis.R” inside the “Supplement. Meta Analysis” folder. 
   - Confirm that "Results" subfolder is inside the "Supplement. Meta Analysis" folder. 
   - Run “Rscript alc\_meta\_analysis.R” in Terminal or the Command Line. 
   - This code performs random-effects meta analyses across text categories and saves the meta-analytic estimates and their 95% confidence intervals as *superior\_meta\_estimate.csv* and *american\_meta\_estimate.csv* in the “Results" subfolder of the “Supplement. Meta Analysis" folder. This code also calculates meta-analytic estimates across group comparisons and the overall meta-analytic estimates for each stereotype dimension. 


#### Visualize meta-analysis results
* Confirm that *acad\_weat\_results.csv*, *blog\_weat\_results.csv*, *fic\_weat\_results.csv*, *mag\_weat\_results.csv*, *news\_weat\_results.csv*, *spok\_weat\_results.csv*, *tvm\_weat\_results.csv*, and *web\_weat\_results.csv* are inside the “Results” subfolder of the “Supplement. Meta Analysis” folder. 
* Execute “meta\_plot.R” inside the "Supplement. Meta Analysis" folder. 
   - Create a "Plots” subfolder inside the “Supplement. Meta Analysis" folder. 
   - Run “Rscript meta\_plot.R” in Terminal or the Command Line. 
   - This code uses the WEAT *D*s and their 95% confidence intervals calculated using the ALC embeddings of group words and COCA embeddings of attribute words and the meta-analytic estimates calculated using random-effects meta analyses to visualize them in single plots (one for each dimension). The plots are saved as *superior\_meta.pdf* and *american\_meta.pdf* in the “Plots" subfolder of the "Supplement. Meta Analysis" folder. 


#### Perform meta-regressions
* Confirm that *acad\_weat\_results.csv*, *blog\_weat\_results.csv*, *fic\_weat\_results.csv*, *mag\_weat\_results.csv*, *news\_weat\_results.csv*, *spok\_weat\_results.csv*, *tvm\_weat\_results.csv*, and *web\_weat\_results.csv* are inside the “Results” subfolder of the “Supplement. Meta Analysis” folder. 
* Execute “alc\_meta\_regression.R” inside the "Supplement. Meta Analysis" folder. 
   - Run “Rscript meta\_regression.R” in Terminal or the Command Line. 
   - This code performs meta-regressions comparing the WEAT *D*s of an individual text category with those of other categories. 


### **Domain Analysis (Supplement. Domain Analysis Folder)** 

#### WEATs defining superiority as intellectual/mental superiority 
* Confirm that *black\_names.csv*, *asian\_names.csv*, *hispanic\_names.csv*, and *white\_names.csv* are inside the "Names70" subfolder of the "Group Word Stimuli” folder and that *intellectual\_mental\_superior.csv*, *intellectual\_mental\_inferior.csv* are inside the “intellectual_mental" subfolder of the “Supplement. Domain Analysis" folder and that *coca.model* is inside the "Embedding Model” folder. 
* Execute “intellectual\_mental\_weat.py” inside the “intellectual_mental” subfolder.  
   - Run “python3 intellectual\_mental\_weat.py” in Terminal or the Command Line. 
   - This code computes the WEAT *D* scores and their 95% confidence intervals for all group comparisons in the superiority/inferiority dimension and saves them as *intellectual\_mental\_weat\_results.csv* in the “intellectual\_mental” subfolder of the “Supplement. Domain Analysis” folder.


#### WEATs defining superiority as moral superiority 
* Confirm that *black\_names.csv*, *asian\_names.csv*, *hispanic\_names.csv*, and *white\_names.csv* are inside the "Names70" subfolder of the "Group Word Stimuli” folder and that *moral\_superior.csv*, *moral\_inferior.csv* are inside the “moral" subfolder of the “Supplement. Domain Analysis" folder and that *coca.model* is inside the "Embedding Model” folder. 
* Execute "moral\_weat.py” inside the “moral” subfolder.  
   - Run “python3 moral\_weat.py” in Terminal or the Command Line. 
   - This code computes the WEAT *D* scores and their 95% confidence intervals for all group comparisons in the superiority/inferiority dimension and saves them as *moral\_weat\_results.csv* in the “moral” subfolder of the “Supplement. Domain Analysis” folder.


#### WEATs defining superiority as social/cultural superiority 
* Confirm that *black\_names.csv*, *asian\_names.csv*, *hispanic\_names.csv*, and *white\_names.csv* are inside the "Names70" subfolder of the "Group Word Stimuli” folder and that *social\_cultural\_superior.csv*, *social\_cultural\_inferior.csv* are inside the “social_cultural" subfolder of the “Supplement. Domain Analysis" folder and that *coca.model* is inside the "Embedding Model” folder. 
* Execute "social\_cultural\_weat.py” inside the “social_cultural” subfolder.  
   - Run “python3 social\_cultural\_weat.py” in Terminal or the Command Line. 
   - This code computes the WEAT *D* scores and their 95% confidence intervals for all group comparisons in the superiority/inferiority dimension and saves them as *social\_cultural\_weat\_results.csv* in the "social\_cultural” subfolder of the “Supplement. Domain Analysis” folder.


#### WEATs defining Americanness as legal status 
* Confirm that *black\_names.csv*, *asian\_names.csv*, *hispanic\_names.csv*, and *white\_names.csv* are inside the "Names70" subfolder of the "Group Word Stimuli” folder and that *legal\_status\_american.csv*, *legal\_status\_foreign.csv* are inside the "legal_status" subfolder of the “Supplement. Domain Analysis" folder and that *coca.model* is inside the "Embedding Model” folder. 
* Execute "legal\_status\_weat.py” inside the “legal_status” subfolder.  
   - Run “python3 legal\_status\_weat.py” in Terminal or the Command Line. 
   - This code computes the WEAT *D* scores and their 95% confidence intervals for all group comparisons in the Americanness/foreignness dimension and saves them as *legal\_status\_weat\_results.csv* in the "legal\_status” subfolder of the “Supplement. Domain Analysis” folder.


### **Alternative Foreignness Word Stimuli (Supplement. Foreignness Word Stimuli Folder)** 

#### Perform WEATs using alternative foreignness word stimuli

* Confirm that *black\_names.csv*, *asian\_names.csv*, *hispanic\_names.csv*, and *white\_names.csv* are inside the "Names70" subfolder of the "Group Word Stimuli” folder and that *american.csv*, *foreign.csv* are inside the "Attribute Word Stimuli" subfolder of the “Supplement. Foreignness Word Stimuli" folder and that *coca.model* is inside the "Embedding Model” folder. 
* Execute "foreignness_weat.py” inside the “Supplement. Foreignness Word Stimuli" folder.  
   - Run “python3 foreignness_weat.py” in Terminal or the Command Line. 
   - This code computes the WEAT *D* scores and their 95% confidence intervals for all group comparisons in the Americanness/foreignness dimension and saves them as *weat\_results\_70.csv* in the "Results” subfolder of the “Supplement. Foreignness Word Stimuli” folder.


### **RIPA (Supplement. RIPA Folder)**

#### Compute RIPA scores
* Confirm that *black\_names.csv*, *asian\_names.csv*, *hispanic\_names.csv*, and *white\_names.csv* are inside the “Names70" subfolder of the “Group Word Stimuli" folder, that *superior.csv*, *inferior.csv*, *american.csv*, and *foreign.csv* are inside the “Word Stimuli" subfolder of the “Attribute Word Stimuli" folder, and that *coca.model*, *coca.model.syn1neg.npy*, and *coca.model.wv.vectors.npy* are inside the "Embedding Model” folder. 
* Execute “ripa.py” inside the "Supplement. RIPA” folder. 
   - Create a “Results” subfolder inside the “Supplement. RIPA" folder. 
   - Run “python3 ripa.py” in Terminal or the Command Line. 
   - This code computes the RIPA *d*s and their 95% confidence intervals for all group comparisons and saves them as a .csv file in the “Results” subfolder of the "Supplement. RIPA” folder. 


#### Visualize RIPA scores
* Confirm that *ripa\_70.csv* is inside the “Results” subfolder of the "Supplement. RIPA" folder. 
* Execute “plot\_ripa.R” inside the "Supplement. RIPA” folder. 
   - Create a “Plots" subfolder inside the “Supplement. RIPA" folder. 
   - Run “Rscript plot\_ripa.R” in Terminal or the Command Line. 
   - This code visualizes superiority and Americanness RIPA *d*s and their 95% confidence intervals as a single plot and saves it in the “Plots" subfolder of the “Supplement. RIPA" folder. 

