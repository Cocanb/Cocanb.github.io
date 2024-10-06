# säl à đmäl à đnonefêf's Algorithm

## Variables

The following variables are needed in order to perform säl à đmäl à đnonefêf's Algorithm.:
- A [stack](https://en.wikipedia.org/wiki/Stack_(abstract_data_type)) of sentence suffixes.
- A stack of quotation/bracket characters
- The current word being processed.
- The output string

## Algorithm

- Iterate over the input text. For each character of the text:
  - If the character is a whitespace (e. g. space, newline, tab, or carriage return) and the current word exists, [process and append the word to the output string](#processing-the-word).
  - If the character is a stop: (e.g. `.`, `?`, or `!`)
    - If the character is a period, check if it is part of a number first.
    - If the current word exists, [process and append the word to the output string](#processing-the-word).
    - Pop the suffix stack and append the result to the output string. (Do NOT push a new suffix onto the stack; this has to be done when processing the start of a new word.)
  - If the character is a quotation mark (e. g. `'` or `"`) or a bracket: (e. g. `(` and `)` or `[` and `]`)
    - If the current word exists, [process and append the word to the output string](#processing-the-word).
    - If the quotes stack is empty or the top does not match with the character, push the character onto the quotes stack and a new suffix (the string `non`) to the suffixes stack. Append the character to the output string.
    - Otherwise, pop both stacks. Append the suffix followed by the character to the output string.
  - If the character is any other punctuation, ignore it.
  - If the character is a digit and the current word does not exist, append the digit to the output string.
  - Otherwise: (i. e. if the character is a letter or a number while the current word exists)
    - If the size of the two stacks are equal, this means a sentence has been terminated and no new sentence has started yet. Push `non` onto the suffixes stack.
    - Append the character to the current word.
- Once you have iterated through the entire text:
  - If the current word variable is not empty, [process and append it to the output string](#processing-the-word).
  - If the suffix stack is not empty, pop the suffix stack and append the result onto the output string.
- Decorate the output.

## Processing the word

- Count the letters of the word, such that numbers are treated as a single character. (see [Rules regarding numbers](./cocanb-guide.md#rules-regarding-numbers)) If the word ends with a number, also determine the position of the start of the number.
- Calculate the quotient (corresponding to the amount of `å`s) and the remainder (corresponding to the length character) of the computed word length divided by `26`.
- Append the word without the final token (the final character or digits) to the output string.
- Append the final token and the length-determining characters to the string at the top of the suffixes stack.
- Clear the current word variable.
