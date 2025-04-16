# HomeAssignment4
Name : Jyostna Marella
ID   :  700761880

1 Ans :

1️. Split the sentence into words
This is called tokenization.
Think of it like cutting the sentence into pieces.
['NLP', 'techniques', 'are', 'used', 'in', 'virtual', 'assistants', 'like', 'Alexa', 'and', 'Siri', '.']
2. Remove common words and punctuation
Words like "are", "in", "and" are used a lot but don’t add much meaning.
Also, punctuation like . is not useful here.
['NLP', 'techniques', 'used', 'virtual', 'assistants', 'like', 'Alexa', 'Siri']
3.Make each word shorter (root form)
This is called stemming.
It cuts words down to their base form.
Example:
"techniques" → "techniqu"
"assistants" → "assist"
['nlp', 'techniqu', 'use', 'virtual', 'assist', 'like', 'alexa', 'siri']


2.Ans :

1.Load the "English Dictionary" (Model)
nlp = spacy.load("en_core_web_sm")
Think of this like loading a robot brain that understands English.
It knows how to find names, places, dates, etc.
2.Give the Robot a Sentence
sentence = "Barack Obama was the 44th President..."
This is the sentence we want the robot to analyze.
3.Robot Scans the Sentence
doc = nlp(sentence)
The robot reads the sentence and understands it.
It splits the sentence into words and tags important things (like names, dates).
4.Robot Tells Us What It Found
for ent in doc.ents:
    print(f"Thing: {ent.text}, Type: {ent.label_}, Where: {ent.start_char}-{ent.end_char}")
The robot says:
Thing: "Barack Obama"
Type: PERSON (because it’s a name)
Where: Starts at character 0, ends at 12

3.Ans  :


Inputs (What We Feed the AI):
Q (Query): What we're currently focusing on ("What word am I looking at now?")
K (Key): All possible words we could pay attention to
V (Value): The actual content of those words

Step 1: Check Relevance
Calculates how much each word (Q) relates to other words (K)
Like asking: "How much does 'President' relate to 'Obama'?"
Step 2: Scale Down
Divides by √(number of dimensions) to keep numbers from getting too big
(Think of it as turning the volume down so we don't get overwhelmed)
Step 3: Softmax Magic
Converts relevance scores into percentages (0-100% attention)
Example output shows:
First word pays 73% attention to first item, 27% to second
Second word does the opposite
Step 4: Create Final Output
Combines the values (V) using these attention percentages
Results in new representations where each word now contains info about related words

4.Ans :

1.Loads a Pre-Trained AI Model
sentiment_pipeline = pipeline("sentiment-analysis")
Uses a ready-made tool (pipeline) from Hugging Face
Automatically downloads a model trained to analyze emotions in text (originally trained on movie reviews)
2.Analyzes a Sentence
result = sentiment_pipeline("Despite the high price, the performance... is outstanding.")
The AI reads the sentence and focuses on key words:
"high price" → Could be negative
"outstanding performance" → Strongly positive
3.Prints the Results
print(f"Sentiment: {result[0]['label']}")  # POSITIVE/NEGATIVE
print(f"Confidence Score: {result[0]['score']:.4f}")  # 0.9998 = 99.98% sure
Output example:
Sentiment: POSITIVE  
Confidence Score: 0.9998  
