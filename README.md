# Recommendation-System
Using Jupyter Notebook within the Jupyter lab enviornment.
I will be using the Walmart Items dataset from PromptCloud on Kaggle. 
- Walmart Product Review Dataset : https://www.kaggle.com/datasets/promptcloud/walmart-product-review-dataset?resource=download

*Python will be the main language used throughout this project

Goal:
Make a product recommendation system using the walmart products. Using content-based, collaborative filtering, hybrid, and multi-model recommendation system approaches to provide diverse recommendations.

 Using the following features from the dataset of 5000 with 32 features:
 Uniq ID, Product ID, Product Rating, Product Reviews Count, Product Category, Product Brand, Product Name, Product Image Url, Product Description, Product Tags.
 Since there are missing values in the data we want to use we will use the fillna() function to fill in the missing values. I used 0 & blank in this case.
    
    data.loc[:, 'Product Category'] = data['Product Category'].fillna('')

Next I want to make the rest of my developmental process easier so I will map names to each column I plan to use in order to make the code easier to write & read.
The last step I will do to prepare the data for data exploration is convert the Uniq Id & Product Id to int or float values the collaborative filtering recommendation system & cosine similarity require.
I changed the format from alphanumeric string to a float string by extracting only the numeric portion of the string. Keeping in mind that some ID values may be completely numeric or letters.

  data['ID'] = data['ID'].str.extract(r'(\d+)').astype(float)
  data['ProdID'] = data['ProdID'].str.extract(r'(\d+)').astype(float)
