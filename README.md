# Big-Data-Project

### Team Memebrs:-

|Number| Name| net-id |
|---|:---| ---:|
|  1 | Suchetha      | ss11436 |
|  2 | Priyanka      | pb1826  |
|  3 | Niranjhana    | nn1024  |

#### Report:
https://docs.google.com/a/nyu.edu/document/d/1WtHlt8fDw-wFNT3u25pt_cLuHJ_yCL7LE5XeIEbfcPs/edit?usp=sharing

#### Dataset:
NYPD Crime (https://data.cityofnewyork.us/Public-Safety/NYPD-Complaint-Data-Historic/qgea-i56i)
Download and save the dataset on to your local machine. Save as "Data.csv"

cleaned.csv: https://1drv.ms/u/s!AnUiz0e7FgpJwTLXrv4zANzPHHxK
Download and save the dataset on to your local machine. Save as "cleaned.csv"

#### Cleaning:

##### General Instructions :

1. Login to Dumbo
2. Setup the following alias :
	* alias hfs='/usr/bin/hadoop fs '
	* export HAS=/opt/cloudera/parcels/CDH-5.9.0-1.cdh5.9.0.p0.23/lib
	* export HSJ=hadoop-mapreduce/hadoop-streaming.jar
	* alias hjs='/usr/bin/hadoop jar $HAS/$HSJ'
3. Upload the dataset to Dumbo
	* On MacOS, open Treminal and run :
		scp data.csv your_netid@dumbo.es.its.nyu.edu:/home/your_netid/
	* On Windows, run cmd.exe and run :
		pscp data.csv your_netid@dumbo.es.its.nyu.edu:/home/your_netid/
	* The file data.csv is already available at  /home/nn1024/
4. Upload the file to hadoop from your local using the command:
	* hadoop fs -copyFromLocal data.csv
	
Instructions to generate cleaned csv for entire dataset :-
5. Run command: 	
  * spark-submit datacleaning.py data.csv
  * hadoop fs -getmerged cleaned.csv cleaned.csv

  OR

Instructions to specific column validation:-
5. Run command: 	
  * spark-submit col0.py data.csv #colNumber_of_feature
   
  * hadoop fs -getmerged dq_col0.out dq_col0.out #x[0],valid(x[0]
    
  * hadoop fs -getmerged count_col0.out count_col0.out #count of the valids,invalids and nulls

#### Data Analysis:

##### General Instructions :

1. Each of the analysis features we used are included folder wise
2. The Jupyter Notebook inside is self-explanatory. All the pyspark scripts, and the graphs are included.
3. All the pyspark scripts were run on cleaned.csv and are called analysis.py
4. The csvs generated by the pyspark script and those generated by the python script in jupyter notebook are also included.


##### Instructions for Dumbo :

1. Login to Dumbo
2. Setup the following alias :
	* alias hfs='/usr/bin/hadoop fs '
	* export HAS=/opt/cloudera/parcels/CDH-5.9.0-1.cdh5.9.0.p0.23/lib
	* export HSJ=hadoop-mapreduce/hadoop-streaming.jar
	* alias hjs='/usr/bin/hadoop jar $HAS/$HSJ'
3. Upload the dataset to Dumbo
	* On MacOS, open Treminal and run :
		scp cleaned.csv your_netid@dumbo.es.its.nyu.edu:/home/your_netid/
	* On Windows, run cmd.exe and run :
		pscp cleaned.csv your_netid@dumbo.es.its.nyu.edu:/home/your_netid/
	* The file cleaned.csv is already available at  /home/nn1024/
4. Upload the file to hadoop from your local using the command:
	* hadoop fs -copyFromLocal cleaned.csv
5. Run command: 	
  * spark-submit analysis.py cleaned.csv
  * hadoop fs -getmerged cleaned.csv cleaned.csv

#### Data Exploration:

##### General Instructions :

1. Each of the exploration topics are included folder wise
2. The Jupyter Notebook inside is self-explanatory.
3. Specific Dates runs directly on the cleaned.csv (link above). This needs to be 
downloaded into the folder as Github had max limits for file upload.


