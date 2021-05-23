# Book Recommendation System
This repository contains modifications and improvements of 
[Book Recommendation System Project](https://www.kaggle.com/willkoehrsen/neural-network-embedding-recommendation-system) 
by Will Koehrsen. This file hold records of any changes made previously.

## April 2021
This month we focused on improving the model by changing moslt parameters. The results were jughed moslt based on the value of loss function, relevance of recomendations and visualizations of embeddings.
### Data cleaning 
The scope of wikilinks provided by the author of the project contains a lot of duplicates. Some wiki link such as ones containing information about if book has a hard or soft cover did not seem relevant to include. 
These links were removed manually. The list of removed links will be listed below.
```
'hardcover', 'paperback', 'hardback', ’e-book', 'wikipedia:wikiproject books', 'wikipedia:wikiproject novels', ’audiobook', 
'amazon.com', 'bbc', 'book', 'ebook', 'random house', 'internet archive', 'worldcat', 'category:random house books', 
'project gutenberg', 'goodreads', 'google books', 'amazon kindle', 'penguin group', 'pseudonym', 'file:', 'vhs', 'dvd', 
'public domain', 'copyright', 'wikipedia:wikiproject novels/novel categorization', 'softcover', 'printing', 
'compact disc', 'author’ ​
```
Additionally links containing information about the year of publish were removed.
After this change most of recommendations remained but the ones that changes still were relevant.

### Loss function 
In oroginal project author used Mean Squared Error to evaluate the loss value. By changing it to Log Cosh function the loss value has deacreased by 56%. 
This was motivated by the fact that Log Cosh is not is not as strongly affected byt outliers as MSE. Although this change improved the loss value the actual importance of outliners 
in recomendation model must be taken into account.

### Value of negative  and positive ratio
- After setting the value of negative ratio to 5 the recomendations remained relevant and the loss function decreased slightly. 
- Setting the value did not change the output values in any significant way.

### Decreasing the embedding size
The value of embeddings was set to 30. The output of such model remained relevant but the value of loss got slighly worse.

### Value of embedding size, positive ratio, negative ratio
The value of embedding size was set to 70, n_positive=2048 and n_negative=5. These changes resulted in
improvement in model in case of loss function and recommendations.