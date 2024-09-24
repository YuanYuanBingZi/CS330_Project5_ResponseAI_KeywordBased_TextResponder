# CS330_Project5_ResponseAI_KeywordBased_TextResponder

## Project Description

ResponseAI is a simple AI program that reads a list of keyword-response pairs, processes a set of messages, and generates responses based on keyword matches. The AI's responses vary depending on its mood (happy or angry), with all results saved to an output file. This project demonstrates basic concepts of object-oriented programming, such as inheritance and polymorphism, by implementing mood-based responses.

## Features

- **Keyword Matching**: The AI scans each message for predefined keywords and generates appropriate responses.
- **Mood-Based Responses**: The AI can respond with either a happy or angry message, based on the associated keyword's mood.
- **Multiple Responses**: If a message contains multiple keywords, the AI generates multiple responses.
- **File Handling**: The program reads inputs from files and writes the results to an output file.

## File Structure

```
.
├── response.h          # Header file with class definitions
├── response.cc         # Class implementation
├── main.cc             # Main program logic
├── Makefile            # Compilation instructions
├── input.txt           # Sample input file containing keyword-response tuples
├── message.txt         # Sample messages file
└── result.txt          # Output file where AI responses are saved
```

## How to Build and Run

### Prerequisites

- Ensure you have access to a C++ compiler and are using the provided `Makefile` to manage the build process.

### Compilation

To compile the program, use the following command in your terminal:

```bash
make
```

### Execution

Once compiled, run the program using the following command, with three file arguments:

```bash
./response_ai <keyword_file> <messages_file> <output_file>
```

- `<keyword_file>`: Contains tuples in the format `<keyword> <response_word> <happiness_flag>`.
- `<messages_file>`: Contains the list of messages to be processed.
- `<output_file>`: File where the AI will store the generated responses.

### Example

```bash
./response_ai input.txt message.txt result.txt
```

This command processes the `input.txt` file, scans the `message.txt` file for keywords, and saves the responses to `result.txt`.

## Implementation Details

- **Response Class**: 
  - Base class that defines the structure for checking and responding to messages.
  - `checkAndRespond`: Scans for keywords in a message and triggers a response.
  - `respond`: Generates a response, which is later overridden by derived classes.

- **HappyResponse Class**:
  - Inherits from `Response` and overrides `respond` to generate a positive message.

- **AngryResponse Class**:
  - Inherits from `Response` and overrides `respond` to generate a negative message.

## Future Enhancements

1. **Advanced Keyword Matching**: Implement case-insensitive or fuzzy keyword matching to improve response flexibility.
2. **Dynamic Mood Adjustment**: Incorporate sentiment analysis to adjust the AI’s mood based on the tone of the messages.
3. **Personalized Responses**: Expand the variety of responses to make interactions more dynamic and less repetitive.

