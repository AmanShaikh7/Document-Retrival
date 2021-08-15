# Document-Retrival

The size of the dataset is too large thats why i'm not able to upload .

you can download it from the link given below 
link for the dataset: https://www.kaggle.com/sameersmahajan/people-wikipedia-data

The following project is done by using turi create library :
lets go from the flow of the project 
step1:
 Import the usefull libraries (here in this case TuriCreate)
 ##if you are using google colab you have to first install it by giving command 
  !pip install turicreate 
  
 the import it by :
 import turicreate as tc
 
 step 2: 
 upload the data set
 
 step 3: 
 Making a dataframe 
 similarly like pandas we also use turicreate for making a dataframe 
 
 df = tc.SFrame('name_of_csv_file.csv')
 
 step 4 :
 Here, in this project first we have used two methods to see which is more efficient
 1) word count
 2) TF-IDF
 
 1) word count :
  for example we have calculate the word count for John Elton
  john['word_count']=tc.text_analytics.count_words(john['text'])
  
  2) similarly for TF-IDF:
  tfidf = tc.text_analytics.tf_idf(people['word_count'])
  
step 5: 
Build a nearest neighbour model :

knn_model1 = tc.nearest_neighbors.create(people,features=['tfidf'],label='name',distance='cosine')

##where 
*people=input to the model
*distance = parameter to find the distance between Knn using cosine

step 6: 
Our model is ready now you can test the model by picking a random article and the finding the most relavant article to it by this model 
 
