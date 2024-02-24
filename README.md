# Forum-QnA-RAG

Converting a Forum QnA into a basic RAG (Retreival Augemented Generation) based search / chat interface

__*extract_forums_data.ipynb*__: Performs 2 steps viz.

1. Get the links to all the forum posts from https://forums.distill.io
2. Visit the top 50 forum post pages and extract various posts & responses on the forum

Subsequently, the data is stored in local CSV files (can be modified to be stored in a database).

__*classify_post_details.ipynb*__: The primary task of this notebook is to classify each forum post by any user among one of the 3 categories viz. 'Question', 'Answer' or 'Statement' using __Cohere's Classify API__. Furthermore, a column in the table is updated with the classifications. *Note that only data from the top 50 pages is extracted and each user post on these pages is classified for illustration purposes.*

__*basic_chatbot.ipynb*__: This notbook has the constructs to build out the chatbot. It has been built upon very similar lines to the example showcased on Cohere's Github repo.
The chatbot is designed to answer the questions listed out int he forum_post_details_with_type.csv file which is generated as an output from the previous notebook.

The general principles above can be applied to any forum & convert it to a chatbot using Cohere's API. 

*Note: Sometimes Cohere's Chat API is very slow to respond and can time out.*