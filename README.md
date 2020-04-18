# Politeness transfer dataset

Dataset for the politeness transfer task


### URL

Available at: https://drive.google.com/file/d/1URNq8vGbhDNBhu_UfD9HrEK8bkgWcqpM/view?usp=sharing


### Sample

|        | msg_id                                        |   sent_id | txt                                                                                                                                                              |      score |   is_useful | p_tag   | split   |
|-------:|:----------------------------------------------|----------:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------:|------------:|:--------|:--------|
| 360990 | <13213843.1075843681416.JavaMail.evans@thyme> |       458 | although it is not illegal under california or u.s. antitrust law for a firm to exercise its market power , it is illegal to do so under the federal power act . | 0.00694478 |           1 | P_0     | test    |
| 534271 | <1494329.1075847456937.JavaMail.evans@thyme>  |         7 | and i have made the changes in profile manager .                                                                                                                 | 0.888002   |           1 | P_8     | train   |
| 812575 | <17935488.1075861200114.JavaMail.evans@thyme> |        12 | investigators think yemeni man was meant to be 20th hijacker                                                                                                     | 0.291539   |           1 | P_2     | train   |
|  41768 | <10338432.1075852561293.JavaMail.evans@thyme> |         2 | we recognize that this is a difficult time in many respects - we would like your input to determine if we have to cancel one or both of these trips .            | 0.969205   |           1 | P_9     | val     |
| 872593 | <18585159.1075845278983.JavaMail.evans@thyme> |        10 | there are two tabs , one tab contains the days                                                                                                                   | 0.618491   |           1 | P_6     | train   |


### Columns 

| Column    	| Definition                                                                                    	| type             	|
|-----------	|-----------------------------------------------------------------------------------------------	|------------------	|
| msg_id    	| Unique email id                                                                               	| str              	|
| sent_id   	| Every sentence in the corpus is assigned a sentence id                                        	| integer          	|
| txt       	| The actual text                                                                               	|                  	|
| score     	| Politeness score                                                                              	| float            	|
| is_useful 	| Whether the sentence is useful. Useful sentences are those that pass all the pruning criteria 	| int (0/1)        	|
| p_tag     	| Politeness tag, assigned based on the politeness score                                        	| str (P_0 to P_9) 	|
| split     	| Split (train/test/dev)                                                                        	| str              	|



### Creation

- The original dataset is located at: https://www.cs.cmu.edu/~./enron/


As discussed in the paper, the following steps were followed to create the dataset:


1. Pre-processing: Tokenization (done using spacy) and conversion to lower case

2. We further prune the corpus by removing the sentences that:
  - were less than 3 words long,
  - had more than 80% numeri-cal tokens,
  - contained email addresses, or
  - had repeatedoccurrences of spurious characters



