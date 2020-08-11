# lncMachine
LncRNA prediction tool for plants

lncMachine requires python3 or newer.

Prediction models was constructed using the sklearn module in version 0.22. Prebuilt models were provided as long as the sklearm module (version 0.22) is used.\n


required python packages:

		Bio
  
		optparse
  
 		numpy
  
  	pandas
  
  	sklearn
  
  	pickle



Options:
  
	--version             show program's version number and exit
  
  
	-h, --help            show this help message and exit
  
  
	-c CODING_FILE, --cod=CODING_FILE
                        
												Coding sequences in fasta format
  
  
	-n NONCODING_FILE, --noncod=NONCODING_FILE
                        
												Noncoding sequences in fasta format. Required for
                        training.
  
  
	--train               Train using coding and noncoding datasets
                        
												[default:RandomForestClassifier(random_state=1,
                        
												n_jobs=-1)]. Both -n and -c required.
  
  
	--all                 Build models for all nine algorithms.
  
  
	--model=PREDICTION_MODEL
                        
												Prediction model in .sav format [optional]
  
  
	--algorithm=ALGORITHM
                        
												Use specified machine learning prediction algorihm
                        
												i.e. RandomForestClassifier(random_state=1, n_jobs=-1)
  
  
	-i ICSV               Tab separated CSV file containing class and feature
												
												information [optional]
  
  
	-o OUTPUT_FILE, --out=OUTPUT_FILE
                        
												Output file name for classification (1 for coding and
                        0 for noncoding) and the features
                        [default:'features.csv'].



--------------------
To build a Random Forest prediction model from a coding and a noncoding data (FASTA):

python3 lncMachine.py -c coding.fasta -n noncoding.fasta --train 


--------------------
To build prediction models using nine machine learning algorithms:

python3 lncMachine.py -c coding.fasta -n noncoding.fasta --train --all


--------------------
To build a Random Forest prediction model from a CSV file containing at least two classes:

python3 lncMachine.py -i features.csv --train


--------------------
To predict coding probability from a FASTA file:

python3 lncMachine.py -c coding.fasta --model prebuiltin_model.sav


--------------------
