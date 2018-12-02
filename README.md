# python-word-count
Extracting most popular words in a document can be pretty challenging without code, especially because stop words (the most common words in a language [i.e. and, or, of, there, all]) aren't usually excluded as they should be when you want to get an accurate representation of your data set. 

## I had to analyze customer reviews based on a company I was a little curious about. I extracted the customer reviews from productreview.com and put them in a .txt file format. Please note that this code worked perfectly for me. After this, I went on to fixing up a table on excel to include these words and their counts, where I eventually visualized a word cloud on Tableau. If any of you rreading this have any insights or comments, please do not hesitate to let me know!


import re
import nltk
## nltk is Python's natural language toolkit. Basically a Python program that works with the human language. I'm not an expert here so I'll avoid explaining any further before I butcher the true definition. 
from nltk.corpus import stopwords
## corpus here is referring to the body of text we want analyzed from our dataset. Notice how we also imported stopwords into python. This will later let us exclude any stopwords found within our dataset in the final output
stopw = set(stopwords.words('english'))
## choosing the english language for stopwords
from collections import Counter
words = re.findall(r'\w+', open('dataset.txt').read().lower())
## I extracted the line of code above from somewhere off the internet, however I'm not quite sure how it was done. I'm still very new to python so any help and insights from the community is much appreciated
filteredfile = [t for t in words if t not in stopw]
stopnull = Counter(filteredfile).most_common(40)
## stopnull is the variable I used to filter out the stopwords for the output. I'm also looking into just showing the top 40. You can adjust however many words you want displayed.
print (stopnull)
