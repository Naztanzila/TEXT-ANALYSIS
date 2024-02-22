# TEXT-ANALYSIS

## Objective

The objective was to extract textual data from given URLs, save the articles in text files, and perform text analysis to compute various variables. The process involves data extraction using Python programming with tools like Beautiful Soup.  Subsequently, textual analysis is conducted to calculate specific variables as outlined in the "Text Analysis" document.

## Data Extraction

Extraction Criteria: Extract only the article title and text, excluding headers, footers, and other irrelevant content.

Tools: Python libraries such as Beautiful Soup.

## Steps

Read URLs from Input file.

Extract article title and text from each URL.

Save the extracted content in text files, using the URL_ID as the filename.

## Data Analysis

Analysis Criteria: Compute specific variables as described in "Text Analysis.docx".

Programming Language: Python

## Variables Computed

1.POSITIVE SCORE

2.NEGATIVE SCORE

3.POLARITY SCORE

4.SUBJECTIVITY SCORE

5.AVG SENTENCE LENGTH

6.PERCENTAGE OF COMPLEX WORDS

7.FOG INDEX

8.COMPLEX WORD COUNT

9.WORD COUNT

10.SYLLABLE PER WORD

## Text Analysis Document

Objective of this document is to explain methodology adopted to perform text analysis to drive sentimental opinion, sentiment scores, readability, passive words, personal pronouns and etc.

A) Sentimental Analysis

-- Sentimental analysis is the process of determining whether a piece of writing is positive, negative, or neutral. The below Algorithm is designed for use in Financial Texts. It consists of steps:

B) Cleaning using Stop Words Lists

--- The Stop Words Lists are used to clean the text so that Sentiment Analysis can be performed by excluding the words found in Stop Words List. 

C) Creating a dictionary of Positive and Negative words

--  Creating a dictionary of Positive and Negative words. We add only those words in the dictionary if they are not found in the Stop Words Lists. 

D) Extracting Derived variables

-- We convert the text into a list of tokens using the nltk tokenize module and use these tokens to calculate the 4 variables described below:

1. Positive Score: This score is calculated by assigning the value of +1 for each word if found in the Positive Dictionary and then adding up all the values.

2. Negative Score: This score is calculated by assigning the value of -1 for each word if found in the Negative Dictionary and then adding up all the values.

   We multiply the score with -1 so that the score is a positive number.

3. Polarity Score: This is the score that determines if a given text is positive or negative in nature. It is calculated by using the formula: 

     Polarity Score = (Positive Score – Negative Score)/ ((Positive Score + Negative Score) + 0.000001)

   Range is from -1 to +1

5. Subjectivity Score: This is the score that determines if a given text is objective or subjective. It is calculated by using the formula: 

   Subjectivity Score = (Positive Score + Negative Score)/ ((Total Words after cleaning) + 0.000001)

   Range is from 0 to +1


E) Analysis of Readability

-- Analysis of Readability is calculated using the Gunning Fox index formula described below.

1. Average Sentence Length = the number of words / the number of sentences

2. Percentage of Complex words = the number of complex words / the number of words 

3. Fog Index = 0.4 * (Average Sentence Length + Percentage of Complex words)


F) Average Number of Words Per Sentence

-- The formula for calculating is:

   Average Number of Words Per Sentence = the total number of words / the total number of sentences


G) Complex Word Count

-- Complex words are words in the text that contain more than two syllables.

H) Word Count

We count the total cleaned words present in the text by 

removing the stop words (using stopwords class of nltk package).

removing any punctuations like ? ! , . from the word before counting.


I) Syllable Count Per Word

We count the number of Syllables in each word of the text by counting the vowels present in each word. We also handle some exceptions like words ending with "es","ed" by not counting 

them as a syllable.


