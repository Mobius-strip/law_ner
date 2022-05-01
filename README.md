# Legal NER 

The aim of this project is to generate useful tags from legal documents.
This information retrival task can be accomplished by named entity recognition.
Here our entities would be legally relavent words.

## Libraries used

1. SpaCY 

SpaCY tags entities which include person, organization, language, event etc. but the legal entites are not inbuilt in it.
However, it gives us the freedom to fine tune the model for custom NER.

2. json 

3. random 


## Data preprocessing 
SpaCY requires the data to be in json format, so the raw text files and their tags are processed so that they are in json format 



#### Processed training data example

```python
['2. Around 46.93 acres of Land was acquired by the Respondent-State of Haryana initiating the proceedings by Notification dated 19.09.1983 issued Under Section 4 of the Land Acquisition Act, 1894. The purpose of acquisition is residential and commercial for Panchkula, Sector-21. The acquired property is in Village Fatehpur. In respect of the same development, we have seen that this Court in many cases has based the fixation of the land value based on acquisition proceedings initiated in 1981 in Village Judian. Those properties in village Judian had access to State Highway and the value fixed by this Court is Rs. 250/- per square yard. In respect of properties situated in the adjoining village of the Appellants namely, Devi Nagar, we have fixed land value at the rate of Rs. 250/- per square yard that was the acquisition initiated in the year 1987 and that property had extensive national highway frontage.',
 {'entities': [(25, 29, 'LAW_ENT'),
   (61, 66, 'LAW_ENT'),
   (108, 120, 'LAW_ENT'),
   (168, 184, 'LAW_ENT'),
   (185, 188, 'LAW_ENT'),
   (564, 569, 'LAW_ENT')]}]
```


## Training custom NER 

We load the empty model and diable all of the other pipeline since our task only involves NER.

By iterating over the training data, the model updates its new weights and get fine tuned for out task.

Model is then saved and the test data is utilized to make predictions 


## Results for a case statement 

```javascript
Special Leave Petition, Land, State, Notification, Land Acquisition, Act, Additional Advocate General, Collector, Motor Vehicles, Tribunal, Union Territory, State Government, Division Bench, District Judge, Award, India, Officer, Executing Court

```
