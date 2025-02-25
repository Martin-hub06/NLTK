!pip install nltk

import nltk
from nltk.tokenize import word_tokenize
from nltk.corpus import stopwords

nltk.download('punkt')
nltk.download('stopwords')

# Task 2: Removing Stop Words
text2 = """Natural Language Toolkit (NLTK) works as a powerful Python 
library that a wide range of tools for Natural Language Processing 
(NLP). From fundamental tasks like text pre-processing to more 
advanced operations such as semantic reasoning, NLTK provides a 
versatile API that caters to the diverse needs of language-related 
tasks."""

stop_words = set(stopwords.words("english"))
words = word_tokenize(text2)
filtered_words = [word for word in words if word.lower() not in stop_words]

print("Text without Stop Words:", " ".join(filtered_words))
