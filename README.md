# Q1Project-Repo

The primary goal of this classification task is to predict the severity of injuries sustained by a non-motorist, such as a pedestrian or cyclist, involved in a car collision. Accurate prediction of injury severity is crucial, as it allows emergency services to assess the urgency and importance of a crash more effectively using data available at the time of dispatch, such as the type of collision, time of day, weather conditions, and location.

By predicting a high severity of injury, dispatchers can allocate additional resources—such as ambulances, paramedics, and specialized equipment—to the crash site even before the first responders arrive. This proactive approach can significantly improve response times for police departments and emergency services, ensuring that those with severe injuries receive the critical care they need more quickly. It also enables better prioritization of multiple incidents, ensuring that the most serious situations receive the attention they require.

Additionally, such predictive models can support data-driven decision-making within emergency management systems, allowing for better planning and resource management over time. For example, identifying patterns in certain types of accidents or locations prone to severe injuries could help guide preventative measures and safety campaigns. Ultimately, this classification model aims to enhance overall public safety, reduce response delays, and improve outcomes for non-motorists involved in collisions.

Description of Files/Folders:
  - INITIAL DATA - the original dataset
  - preprocessed data -  the data after preprocessing, before filling missing values
  - crash_data.csv: this is the preprocessed data WITH the missing values filled in from WEKA, and this is what is used to make the train/test data
  - train/test data: all the training and testing data sets for each attribute selection algorithm are here, under the folders of their respective names. train.csv and test.csv represent the train/test data before the non selected attributes were removed

Pre-processing was done on Google Sheets, and Weka was used to visualize the missing values and values for each attribute

How to Reproduce Our Models (e.g. OneR):
  1. download crash_data.csv
  2. run the colab script to get train/test data, and download those files as train.csv and test.csv respectively
  3. open crash_data.csv in weka and in the “Select attributes” tab, select OneRAttributeEval and use Ranker as a search method
  4. If “Injury Severity” is not already the class, then go to the Preprocess tab, click “Edit” and then right click on “Injury Severity” and select “Attribute as class.” Do this for all future files as well if Injury Severity is not already selected as the class
       - Run this, and select all attributes with a cutoff value of 44.5 or higher
  5. open test.csv, and remove all attributes that were not selected by the OneRAttributeEval. save this as test1R.csv
  6. open train.csv, and remove all attributes that were not selected by the OneRAttributeEval. save this as train1R.csv
  7. go to the “classify” tab, and choose Random Forest (under trees)
  8. select “Supplied test set”, choose test1R.csv, make sure “Injury Severity” is the class, and press start. If a warning comes up, press yes.


