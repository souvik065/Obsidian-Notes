

# Common Techniques in Feature Engineering

## Common Techniques in Feature Engineering

### **1. One-Hot Encoding**:
[One-Hot Encoding](https://www.geeksforgeeks.org/machine-learning/ml-one-hot-encoding/) converts categorical variables into binary indicators, allowing them to be used by machine learning models.
```python
import pandas as pd

data = {'Color': ['Red', 'Blue', 'Green', 'Blue']}
df = pd.DataFrame(data)

df_encoded = pd.get_dummies(df, columns=['Color'], prefix='Color')

print(df_encoded)
```
  
**Output**
```text
   Color_Blue  Color_Green  Color_Red
0       False        False       True
1        True        False      False
2       False         True      False
3        True        False      False
```

### **2. Binning**:
[Binning](https://www.geeksforgeeks.org/machine-learning/binning-in-data-mining/) transforms continuous variables into discrete bins, making them categorical for easier analysis.
```python
import pandas as pd

data = {'Age': [23, 45, 18, 34, 67, 50, 21]}
df = pd.DataFrame(data)

bins = [0, 20, 40, 60, 100]
labels = ['0-20', '21-40', '41-60', '61+']

df['Age_Group'] = pd.cut(df['Age'], bins=bins, labels=labels, right=False)

print(df)
```
  
**Output**
```text
   Age Age_Group
0   23     21-40
1   45     41-60
2   18      0-20
3   34     21-40
4   67       61+
5   50     41-60
6   21     21-40
```

### **3. Text Data Preprocessing**:
Involves removing [stop-words](https://www.geeksforgeeks.org/nlp/removing-stop-words-nltk-python/), [stemming](https://www.geeksforgeeks.org/machine-learning/introduction-to-stemming/) and [vectorizing](https://www.geeksforgeeks.org/nlp/vectorization-techniques-in-nlp/) text data to prepare it for machine learning models.
```python
import nltk
from nltk.corpus import stopwords
from nltk.stem import PorterStemmer
from sklearn.feature_extraction.text import CountVectorizer

texts = ["This is a sample sentence.", "Text data preprocessing is important."]

stop_words = set(stopwords.words('english'))
stemmer = PorterStemmer()
vectorizer = CountVectorizer()


def preprocess_text(text):
    words = text.split()
    words = [stemmer.stem(word)
             for word in words if word.lower() not in stop_words]
    return " ".join(words)


cleaned_texts = [preprocess_text(text) for text in texts]

X = vectorizer.fit_transform(cleaned_texts)

print("Cleaned Texts:", cleaned_texts)
print("Vectorized Text:", X.toarray())
```

****Output:****

![output](https://media.geeksforgeeks.org/wp-content/uploads/20250701113324922110/output.webp "Click to enlarge")

****4. Feature Splitting****: Divides a single feature into multiple sub-features, uncovering valuable insights and improving model performance.
```python
import pandas as pd

data = {'Full_Address': [
    '123 Elm St, Springfield, 12345', '456 Oak Rd, Shelbyville, 67890']}
df = pd.DataFrame(data)

df[['Street', 'City', 'Zipcode']] = df['Full_Address'].str.extract(
    r'([0-9]+\s[\w\s]+),\s([\w\s]+),\s(\d+)')

print(df)
```
**Output**
```text

                     Full_Address      Street         City Zipcode
0  123 Elm St, Springfield, 12345  123 Elm St  Springfield   12345
1  456 Oak Rd, Shelbyville, 67890  456 Oak Rd  Shelbyville   67890...
```



---

## Tools for Feature Engineering

There are several tools available for feature engineering. Here are some popular ones:

- ****Featuretools****: Automates feature engineering by extracting and transforming features from structured data. It integrates well with libraries like pandas and scikit-learn making it easy to create complex features without extensive coding.
- ****TPOT****: Uses genetic algorithms to optimize machine learning pipelines, automating feature selection and model optimization. It visualizes the entire process, helping you identify the best combination of features and algorithms.
- ****DataRobot****: Automates machine learning workflows including feature engineering, model selection and optimization. It supports time-dependent and text data and offers collaborative tools for teams to efficiently work on projects.
- ****Alteryx****: Offers a visual interface for building data workflows, simplifying feature extraction, transformation and cleaning. It integrates with popular data sources and its drag-and-drop interface makes it accessible for non-programmers.
- ****H2O.ai****: Provides both automated and manual feature engineering tools for a variety of data types. It includes features for scaling, imputation and encoding and offers interactive visualizations to better understand model results.


----


**Source : `ChatGPT` Account :** bhattacharyasouvik065@gmail.com
[Chat-1](https://chatgpt.com/share/6999b73a-fde0-800a-87a5-f46c36da47c8)
