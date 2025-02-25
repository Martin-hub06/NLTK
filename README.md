# Task 1: Tokenization (Words and Sentences)
!pip install nltk

import nltk
from nltk.tokenize import word_tokenize, sent_tokenize
from nltk.corpus import stopwords
import string

nltk.download('punkt')
nltk.download('stopwords')


text1 = """Natural Language Toolkit (NLTK) is one of the largest Python 
libraries for performing various Natural Language Processing tasks. 
From rudimentary tasks such as text pre-processing to tasks likes 
vectorized representation of text – NLTK’s API has covered 
everything."""

sentences = sent_tokenize(text1)
words = word_tokenize(text1)

print("Tokenized Sentences:", sentences)
print("\nTokenized Words:", words)

# Task 2: Removing Stop Words
!pip install nltk

import nltk
from nltk.tokenize import word_tokenize
from nltk.corpus import stopwords

nltk.download('punkt')
nltk.download('stopwords')


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


# Task 3: Convert to Lowercase and Remove Punctuation
!pip install nltk

import string


text3 = """Let’s eat, Grandma!
Grandma, Let’s eat!
Silvia, Are you free tomorrow?
Yes, I’m free on Saturday."""


text3_lower = text3.lower()


text3_clean = text3_lower.translate(str.maketrans("", "", string.punctuation))

print("Lowercase and Punctuation Removed:\n", text3_clean)

# Task 4: Clean Text (Remove Extra Whitespaces & Special Characters)

!pip install nltk

import re


text4 = """ @@Natural Language Processing (NLP)!!! is a field of AI that 
focuses on ... 
 enabling computers to understand, interpret, & generate human 
language. 
 NLP includes tasks like *tokenization, lemmatization,* && 
sentiment analysis. 
 It helps in applications such as chatbots, machine translation, 
and voice assistants!!! 
 However, cleaning text—removing extra spaces, punctuations, && 
special $$$ characters—is crucial. 
 Without preprocessing, NLP models may not perform 
accurately !!! 
 So, can you clean this messy text & make it structured??? """


cleaned_text = re.sub(r"[^a-zA-Z0-9\s]", "", text4)  
cleaned_text = re.sub(r"\s+", " ", cleaned_text).strip()  

print("Cleaned Text:\n", cleaned_text)

# Task 5: Stemming and Lemmatization
!pip install nltk

import nltk
from nltk.tokenize import word_tokenize
from nltk.stem import PorterStemmer, WordNetLemmatizer

nltk.download('punkt')
nltk.download('wordnet')

text5 = """The researchers are analyzing various datasets to study the effects 
of automation. 
They observed that automated systems perform tasks more 
efficiently than humans. 
Many industries have been adopting AI-driven solutions to improve 
productivity. 
Running complex algorithms helps in predicting future trends 
accurately. 
Several companies are investing in developing smarter and more 
adaptive models. 
Data scientists continuously refine their models to achieve better 
performance. 
The advancements in technology have transformed the way 
businesses operate."""

words = word_tokenize(text5)

stemmer = PorterStemmer()
lemmatizer = WordNetLemmatizer()

stemmed_words = [stemmer.stem(word) for word in words]
lemmatized_words = [lemmatizer.lemmatize(word) for word in words]

print("Original Words:", words)
print("\nStemmed Words:", stemmed_words)
print("\nLemmatized Words:", lemmatized_words)

