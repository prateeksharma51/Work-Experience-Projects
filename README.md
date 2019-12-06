# Work-Experience-Projects
Since the nature of my project restricts me from sharing the data that I have worked on as It is Confidential I am going to share snippets of the work that I did and walk through the process I followed. 
- Project Required people to manually analyse data on Excel sheets and label the rows as 'valid_mapping' if the columns representing "Customer Details" and "Party Details" had similar records like their names and addresses. 
### Here is a List of features :
['CUSTOMER_ID', 'ADDRESS_ID', 'SITE_ID', 'SOURCE_SYSTEM_NAME',
 'CUSTOMER_NAME', 'ADDRESS1', 'ADDRESS2', 'ADDRESS3', 'ADDRESS4', 'CITY',
 'STATE', 'PROVINCE', 'POSTAL_CODE', 'COUNTRY', 'PARTY_ID', 'PARTY_NAME',
 'PARTY_ADDRESS1', 'PARTY_ADDRESS2', 'PARTY_ADDRESS3', 'PARTY_ADDRESS4',
 'PARTY_CITY', 'PARTY_COUNTY', 'PARTY_STATE', 'PARTY_PROVINCE',
 'PARTY_COUNTRY_CODE', 'GU_ID', 'GU_NAME', 'ASSET_COUNT',
 'CORRECTION_REQUIRED_Y_N', 'ACTION_STATUS', 'TYPE OF ANLAYSIS',
 'TARGET IDENTIFICATION', 'Analyis details', 'REMARKS', 'LINKS',
 'TARGET_PARTY_ID', 'CREATED_PARTY_ID', 'SUGGESTED SITE ID', 'GU ID',
 'SUGGESTED_ACTION', 'ADDITIONAL COMMENTS']
 - I was given the same task of manually labeling the dataset which, I thought could be easily automated and hence I went forward and built an XGBoost Classifier that was able to classify the points as valid_mapping with 97% test accuracy. 
### Feature engineered the data by evaluating a smorgasbord of similarity metrics like :
- Token Sort Ratio 

- Token Set Ratio 
![Token Set Ratio](https://github.com/prateeksharma51/Work-Experience-Projects/blob/master/Images/token_set_ratio_bw_addresses_extended.png)
- Fuzz Ratio 

- Fuzz Partial Ratio 

- Levenshtein distance
![Levenshtein distance](https://github.com/prateeksharma51/Work-Experience-Projects/blob/master/Images/Levenshtein_distance_bw_addresses_extended.png)
![Levenshtein distance](https://github.com/prateeksharma51/Work-Experience-Projects/blob/master/Images/Levenshtein_distance_bw_names.png)

- Hamming Distance 
![Hamming Distance](https://github.com/prateeksharma51/Work-Experience-Projects/blob/master/Images/hamming_distance_bw_addresses_extended.png)

- Cosine Similarity
- jarowinkler_Distance

- Also vectorized the categorical data in fileds like "City", "Country" e.t.c. 

### Applid Logistic regression On the dataset, did hyperparamater tuning and managed to get a test log loss of 0.1221
![Logistic Regression](https://github.com/prateeksharma51/Work-Experience-Projects/blob/master/Images/Screenshot%20(3).png)
### Given the good result after merely applying Logisic regression led me to apply xgboost on the same and ended up with a Test Accuracy of 0.9733 and AUC Score of 0.977646. 
![XGBoost](https://github.com/prateeksharma51/Work-Experience-Projects/blob/master/Images/Screenshot%20(4).png)
