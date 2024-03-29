# Text Summarizer

This is a text summarizer application written in Python and powered by the Natural Language Toolkit (NLTK). It takes in a piece of text and provides a random summary by selecting the most essential sentences based on word frequencies.

## Features

- Uses NLTK for tokenization, stop word removal, and frequency calculation
- Generates a summary by selecting the top sentences based on word frequencies
- Introduces randomness to provide a different result each time it runs


## Requirements

-   Python 3.x
-   NLTK library (`nltk`)
-   NLTK data (specifically the `stopwords` corpus)
## Installation

1.  Clone the repository or download the script directly.
2.  Install the required dependencies by running the following command:
    
    Copy code
    
    `pip install nltk` 
    
3.  Download the necessary NLTK data by executing the following code snippet in a Python shell or script:
    
    pythonCopy code
    
    `import nltk
    nltk.download('stopwords')
    nltk.download('punkt')` 
    

## Usage

The script provides a function called `text_summarizer` that takes in two parameters: `text` (the input text to be summarized) and `num_sentences` (the desired number of sentences in the summary, defaults to 3 if not specified).

Here's an example usage of the script:

pythonCopy code

`import random
from nltk.corpus import stopwords
from nltk.tokenize import word_tokenize, sent_tokenize
from nltk.probability import FreqDist

def text_summarizer(text, num_sentences=3):
    # Implementation details...

# Example usage

text = """
Instead of importing the whole nltk module, I simply imported the essential submodules (stopwords, word_tokenize, sent_tokenize, and FreqDist), which reduced unnecessary memory usage and improved efficiency.

To make the code cleaner and easier to read, I deleted self-explanatory comments.

NLTK includes a FreqDist class for calculating word frequencies. I used it directly on the list of words, eliminating the need to manually cycle through each word and update the frequency distribution.

To simplify the code, I used list comprehension instead of a standard for loop to calculate sentence scores and added randomness into the selection process of the top sentences.
"""

summary = text_summarizer(text)
print(summary)` 

In the example above, the `text_summarizer` function is called with the input `text`, which contains the text to be summarized. The resulting summary is then printed to the console.

You can modify the `num_sentences` parameter to specify the desired number of sentences in the summary. By default, it is set to 3.

Feel free to adjust the code and experiment with different texts to generate summaries for your specific needs.
## How It Works

The input text is divided into sentences using the NLTK sent_tokenize function.

The sentences are tokenized into words using the word_tokenize function.

Stop words (common words without significant meaning) are removed using the NLTK stopwords corpus.

Word frequencies are calculated using the NLTK FreqDist class.

Each sentence is assigned a score based on the sum of word frequencies.

The sentences are sorted in descending order of scores.

The top num_sentences sentences are selected for the summary.

The summary is generated by joining the selected sentences.


-   The script utilizes NLTK's `stopwords` corpus to remove common words that do not contribute significantly to the meaning of the text.
-   The frequency distribution of words is calculated using NLTK's `FreqDist` class, which provides a convenient way to count word occurrences.
-   The script randomly selects the top sentences based on their scores to introduce variability in the generated summaries.
-   The output summary is created by concatenating the selected sentences from the input text.

# Example usage

text = """
Instead of importing the whole nltk module, I simply imported the essential submodules (stopwords, word_tokenize, sent_tokenize, and FreqDist), which reduced unnecessary memory usage and improved efficiency.

To make the code cleaner and easier to read, I deleted self-explanatory comments.

NLTK includes a FreqDist class for calculating word frequencies. I used it directly on the list of words, eliminating the need to manually cycle through each word and update the frequency distribution.

To simplify the code, I used list comprehension instead of a standard for loop to calculate sentence scores.
"""

summary = text_summarizer(text)
print(summary)` 

Replace the `text` variable with your own input text and adjust the `num_sentences` parameter if needed. Running the code will generate a summary based on the input text.

## Contributing
Contributions are welcome! If you have any suggestions, bug reports, or feature requests, please open an issue or submit a pull request.

## License
This script is released under the [MIT License](https://chat.openai.com/LICENSE). Feel free to modify and use it according to your needs.

Please note that the NLTK library has its own license terms, which you should review separately if you plan to use it in your projects.