
# Text Summarizer

Using Natural Language Processing (NLP) approaches, this Python software provides basic text summarizing functionality. The script examines a text and provides a brief summary by selecting the most important sentences.

## Specifications

- Using NLTK (Natural Language Toolkit), tokenizes the text into sentences and words.
- Removes stop words to remove extraneous words - Determines word frequencies using the NLTK FreqDist module
- Scores sentences based on word frequency.
- Chooses the top sentences with the highest summaries.

### Setup

1. Make sure Python is installed on your system.
2. Execute the following command to install the appropriate NLTK library:
   
    Copy code
    
    `pip install nltk` 
    
3.  Download the necessary NLTK resources by running the Python shell:
    
    pythonCopy code
    
    `import nltk
    nltk.download('punkt')
    nltk.download('stopwords')` 
    

## Usage

pythonCopy code

``import nltk
from nltk.corpus import stopwords
from nltk.tokenize import word_tokenize, sent_tokenize
from nltk.probability import FreqDist

def text_summarizer(text, num_sentences=3):
    # Tokenize the text into sentences
    sentences = sent_tokenize(text)

    # Tokenize the text into words
    words = word_tokenize(text.lower())

    # Remove stop words
    stop_words = set(stopwords.words("english"))
    filtered_words = [word for word in words if word.casefold() not in stop_words]

    # Calculate word frequencies
    fdist = FreqDist(filtered_words)

    # Assign scores to sentences based on word frequencies
    sentence_scores = {}
    for i, sentence in enumerate(sentences):
        for word in word_tokenize(sentence.lower()):
            if word in fdist:
                if i in sentence_scores:
                    sentence_scores[i] += fdist[word]
                else:
                    sentence_scores[i] = fdist[word]

    # Sort sentences by scores in descending order
    sorted_sentences = sorted(sentence_scores, key=lambda x: sentence_scores[x], reverse=True)

    # Select the top `num_sentences` sentences for the summary
    summary_sentences = sorted(sorted_sentences[:num_sentences])

    # Create the summary
    summary = ' '.join([sentences[i] for i in summary_sentences])

    return summary`` 


To utilize the 'text_summarizer' function, supply the text to be summarized as the first argument. You can use the 'num_sentences' argument to specify the number of sentences you want in the summary.

Python code

'text = "..." summary = text_summarizer(text, num_sentences=3) print(summary)' 

## Examples

Python code

'text = "..." summary = text_summarizer(text, num_sentences=3) print(summary)' 

## Contributing

Contributions are welcome! If you identify any bugs or have recommendations for improvements, please start an issue or send a pull request.

## Authorization

This project is released under the MIT License. More information is available in the [LICENSE](https://chat.openai.com/LICENSE) file.

## Acknowledgements

This script is inspired by the field of Natural Language Processing (NLP) and makes use of the NLTK library. Thank you to the NLTK team for creating such a great resource for NLP tasks.