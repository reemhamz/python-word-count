import re
import nltk
from nltk.corpus import stopwords
stopw = set(stopwords.words('english'))
from collections import Counter
words = re.findall(r'\w+', open('star_ratings.txt').read().lower())
filteredfile = [t for t in words if t not in stopw]
stopnull = Counter(filteredfile).most_common(40)
print (stopnull)
