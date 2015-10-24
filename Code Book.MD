#Getting and Cleaning Data Project Code Book


##The Data Files

- 'features.txt': List of all features.

- 'activity_labels.txt': Links the class labels with their activity name.

- 'train/X_train.txt': Training data set.

- 'train/y_train.txt': Training labels.

- 'test/X_test.txt': Test data set.

- 'test/y_test.txt': Test labels.

- 'train/subject_train.txt': Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30. 

- 'test/subject_test.txt': Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30. 

- 'AvgSubActData.txt': This was the outputfile from the analysis of run_analysis.R

Notes: 
======
- Features are normalized and bounded within [-1,1].
- Each feature vector is a row on the text file.

##Table Variables

This section will outline the table viables that were created for the final dataset

The Datapoints in the variables are the measurement for the device for a speicifc Axis (X, Y, Z)

"Subject"  : Individual the measurments were captured for                                         
"Activity" : Activity the indvidual was perfomring when the measurements was captured

### Measurements that were captured

"FrequencyBodyAccelerometerJerkMean-X-Axis"      
"FrequencyBodyAccelerometerJerkMean-Y-Axis"       
"FrequencyBodyAccelerometerJerkMean-Z-Axis"       
"FrequencyBodyAccelerometerJerkStd-X-Axis"       
"FrequencyBodyAccelerometerJerkStd-Y-Axis"        
"FrequencyBodyAccelerometerJerkStd-Z-Axis"        
"FrequencyBodyAccelerometerMagnitudeMean"        
"FrequencyBodyAccelerometerMagnitudeStd"          
"FrequencyBodyAccelerometerMean-X-Axis"           
"FrequencyBodyAccelerometerMean-Y-Axis"          
"FrequencyBodyAccelerometerMean-Z-Axis"           
"FrequencyBodyAccelerometerStd-X-Axis"            
"FrequencyBodyAccelerometerStd-Y-Axis"           
"FrequencyBodyAccelerometerStd-Z-Axis"            
"FrequencyBodyBodyAccelerometerJerkMagnitudeMean"<br> 
"FrequencyBodyBodyAccelerometerJerkMagnitudeStd" <br>
"FrequencyBodyBodyGyroscopeJerkMagnitudeMean"<br>
"FrequencyBodyBodyGyroscopeJerkMagnitudeStd"      
"FrequencyBodyBodyGyroscopeMagnitudeMean"        
"FrequencyBodyBodyGyroscopeMagnitudeStd"          
"FrequencyBodyGyroscopeMean-X-Axis"               
"FrequencyBodyGyroscopeMean-Y-Axis"              
"FrequencyBodyGyroscopeMean-Z-Axis"               
"FrequencyBodyGyroscopeStd-X-Axis"                
"FrequencyBodyGyroscopeStd-Y-Axis"               
"FrequencyBodyGyroscopeStd-Z-Axis"                
"TimeBodyAccelerometerJerkMagnitudeMean"          
"TimeBodyAccelerometerJerkMagnitudeStd"          
"TimeBodyAccelerometerJerkMean-X-Axis"            
"TimeBodyAccelerometerJerkMean-Y-Axis"            
"TimeBodyAccelerometerJerkMean-Z-Axis"           
"TimeBodyAccelerometerJerkStd-X-Axis"             
"TimeBodyAccelerometerJerkStd-Y-Axis"             
"TimeBodyAccelerometerJerkStd-Z-Axis"            
"TimeBodyAccelerometerMagnitudeMean"              
"TimeBodyAccelerometerMagnitudeStd"               
"TimeBodyAccelerometerMean-X-Axis"               
"TimeBodyAccelerometerMean-Y-Axis"                
"TimeBodyAccelerometerMean-Z-Axis"                
"TimeBodyAccelerometerStd-X-Axis"                
"TimeBodyAccelerometerStd-Y-Axis"                 
"TimeBodyAccelerometerStd-Z-Axis"                 
"TimeBodyGyroscopeJerkMagnitudeMean"             
"TimeBodyGyroscopeJerkMagnitudeStd"               
"TimeBodyGyroscopeJerkMean-X-Axis"                
"TimeBodyGyroscopeJerkMean-Y-Axis"               
"TimeBodyGyroscopeJerkMean-Z-Axis"                
"TimeBodyGyroscopeJerkStd-X-Axis"                 
"TimeBodyGyroscopeJerkStd-Y-Axis"                
"TimeBodyGyroscopeJerkStd-Z-Axis"                 
"TimeBodyGyroscopeMagnitudeMean"                  
"TimeBodyGyroscopeMagnitudeStd"                  
"TimeBodyGyroscopeMean-X-Axis"                    
"TimeBodyGyroscopeMean-Y-Axis"                    
"TimeBodyGyroscopeMean-Z-Axis"                   
"TimeBodyGyroscopeStd-X-Axis"                     
"TimeBodyGyroscopeStd-Y-Axis"                     
"TimeBodyGyroscopeStd-Z-Axis"                    
"TimeGravityAccelerometerMagnitudeMean"           
"TimeGravityAccelerometerMagnitudeStd"            
"TimeGravityAccelerometerMean-X-Axis"            
"TimeGravityAccelerometerMean-Y-Axis"             
"TimeGravityAccelerometerMean-Z-Axis"             
"TimeGravityAccelerometerStd-X-Axis"             
"TimeGravityAccelerometerStd-Y-Axis"              
"TimeGravityAccelerometerStd-Z-Axis"  

##Code Variables

###files

Xtr : X_Training File

Ytr : Y_Training File

Str : Subject_Training File

Vlt : Features File

Xte : X_Test File

Yte : Y_Test File

Ste : Subject_Test File

anames : activity_lables file

###Data.Tables

Train : Combined Training Files (Xtr, Ytr, Str)

Test : Combined Test Files (Xte, Yte, Ste)

mData : Merged Training and Test Data Tables

clist : Cut mData for Std & Mean measurements

cmData : mData Data Table with updated factors for anames data table

acmData : Sumarized (Mean) cmData Data table by Subject by activity 


###Other

nc : number of columns in mData used to add column labels

x : for variable

col_idx : column index for Subject used to pull it to the front of the Data Table



##Misc

The code is well documented.  The basic flow is as follows:
1) Download Project Data
2) UnZip Project Data
3) Load and Merge Training and Test Data set
4) Merge Training Data Set with Test Data Set
5) Trim Data Set to include only std() and mean() columns
6) Apply Activity labels to activity factor
7) Cleanup column names and make them readable
8) Average final data set by Subject by Activity

Each Step is documented in the code…
