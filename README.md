# Text Summarizer

This is a text summarizer application written in Python and powered by the Natural Language Toolkit (NLTK). It takes in a piece of text and provides a random summary by selecting the most essential sentences based on word frequencies.

## Features

- Uses NLTK for tokenization, stop word removal, and frequency calculation
- Generates a summary by selecting the top sentences based on word frequencies
- Introduces randomness to provide a different result each time it runs

## Installation

1. Make sure you have Python 3.x installed on your system.
2. Clone this repository:

   ```shell
   git clone https://github.com/your-username/text-summarizer.git

3.  Install the required dependencies using pip:
    
    shellCopy code
    
    `pip install -r requirements.txt`
## Usage

pythonCopy code

`from text_summarizer import text_summarizer

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

## License

This project is licensed under the [MIT License](https://chat.openai.com/c/LICENSE).

Feel free to contribute, report issues, or suggest improvements by creating a pull request or submitting an issue.