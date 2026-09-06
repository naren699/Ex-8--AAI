<H3>ENTER YOUR NAME : NARENDHIRAN P</H3>
<H3>ENTER YOUR REGISTER NO : 212224230177</H3>
<H3>EX. NO.08</H3>
<H3>DATE: 06/09/2026</H3>
<H1 ALIGN =CENTER>Implementation of Semantic Analysis</H1>
<H3>Aim: to perform Parts of speech identification and Synonym using Natural Language Processing (NLP) techniques. </H3> 
 <BR>
<h3>Algorithm:</h3>
Step 1: Import the nltk library.<br>
Step 2: Download the 'punkt', 'wordnet', and 'averaged_perceptron_tagger' resources.<br>
Step 3:Accept user input for the text.<br>
Step 4:Tokenize the input text into words using the word_tokenize function.<br>
Step 5:Iterate through each word in the tokenized text.<br>
•	Perform part-of-speech tagging on the tokenized words using nltk.pos_tag.<br>
•	Print each word along with its corresponding part-of-speech tag.<br>
•	For each verb , iterate through its synsets (sets of synonyms) using wordnet.synsets(word).<br>
•	Extract synonyms and antonyms using lemma.name() and lemma.antonyms()[0].name() respectively.<br>
•	Print the unique sets of synonyms and antonyms.
<H3>Program:</H3>

```PY
pip install nltk

import nltk
nltk.download('punkt')
from nltk.tokenize import word_tokenize
nltk.download('averaged_perceptron_tagger')

import nltk
from nltk.tokenize import word_tokenize
from nltk.corpus import wordnet

nltk.download('punkt')
nltk.download('punkt_tab')
nltk.download('averaged_perceptron_tagger_eng')
nltk.download('wordnet')

sentence = input()
# Tokenize the sentence into words
words = word_tokenize(sentence)

# Identify the parts of speech for each word
tagged_words = nltk.pos_tag(words)

# Print the parts of speech
print(tagged_words)

# Save verbs in a list
Veb_words = []
for word, tag in tagged_words:
    if tag.startswith('VB'):
        Veb_words.append(word)

print("Verb",Veb_words)

# Identify synonyms and antonyms for each word
from nltk.corpus import wordnet

synonyms = []
antonyms = []
for word in Veb_words:
    for syn in wordnet.synsets(word):
        for lemma in syn.lemmas():
            synonyms.append(lemma.name())
            if lemma.antonyms():
                antonyms.append(lemma.antonyms()[0].name())

# Print the synonyms and antonyms
print("Synonyms:", set(synonyms))
print("Antonyms:", set(antonyms))

```

<H3>Output</H3>

<img width="1310" height="43" alt="image" src="https://github.com/user-attachments/assets/4199168b-0d59-4575-b6f8-a18d0c75f93b" />

<img width="162" height="27" alt="image" src="https://github.com/user-attachments/assets/403104ac-0651-4367-a299-5bfd98893577" />

```
Synonyms: {'rise', 'saltation', 'jump', 'chute', 'spring', 'jump_out', 'bound', 'stand_out', 'startle', 'jumpstart', 'parachute', 'derail', 'jumping', 'jump-start', 'skip_over', 'jump_off', 'leap_out', 'skip', 'parachuting', 'leap', 'alternate', 'start', 'climb_up', 'pass_over', 'stick_out'}
Antonyms: set()
```



<H3>Result:</H3>
Thus ,the program to perform the Parts of Speech identification and Synonymis executed sucessfully.
