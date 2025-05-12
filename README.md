# Gemma 2B Text Generation with Transformers

[![Python Version](https://img.shields.io/badge/python-3.10-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Transformers-orange)](https://huggingface.co/docs/transformers/index)

This repository demonstrates the implementation of Google's Gemma 2B language model using the Hugging Face Transformers library. The model is capable of performing various natural language processing tasks, including text generation and question answering.

## Table of Contents
- [Overview](#overview)
- [Requirements](#requirements)
- [Setup](#setup)
- [Usage](#usage)
- [Features](#features)
- [Examples](#examples)
- [Contact](#contact)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Overview

The Gemma model is a powerful language model that can be used for various NLP tasks. In this implementation, we showcase:
- Text generation capabilities
- Question answering functionality
- Easy integration with the Hugging Face Transformers library

## Requirements

To run this notebook, you'll need the following dependencies:
```bash
pip install --upgrade huggingface_hub
pip install git+https://github.com/huggingface/transformers -U
pip install accelerate
pip install bitsandbytes
```

## Setup

1. Clone this repository:
```bash
git clone https://github.com/Yossefmohammed/transformers-Gemma-generation-2b-v1.git
cd transformers-Gemma-generation-2b-v1
```

2. Install the required dependencies:
```bash
pip install -r requirements.txt  # If you have a requirements.txt file
# OR
pip install --upgrade huggingface_hub transformers accelerate bitsandbytes
```

3. Make sure you have access to the Gemma model weights:
   - Create a Hugging Face account if you don't have one
   - Get your Hugging Face token from your account settings
   - Set up authentication using:
   ```python
   from huggingface_hub import login
   login("your_token_here")
   ```

## Usage

The notebook demonstrates how to:
1. Load the Gemma 2B model and tokenizer
2. Generate text responses
3. Answer questions using the model

Example usage:
```python
from transformers import AutoTokenizer, AutoModelForCausalLM

# Load the model and tokenizer
tokenizer = AutoTokenizer.from_pretrained("path_to_model")
model = AutoModelForCausalLM.from_pretrained("path_to_model")

# Generate text
input_text = "Your input text here"
input_ids = tokenizer(input_text, return_tensors="pt", truncation=True, padding=True)
output = model.generate(input_ids["input_ids"], max_length=60)
print(tokenizer.decode(output[0], skip_special_tokens=True))
```

## Features

- Text generation with customizable parameters
- Question answering capabilities
- Easy-to-use interface with Hugging Face Transformers
- Support for various input formats
- Efficient model loading and inference
- Customizable generation parameters

## Examples

Here are some example outputs from the model:

1. Question Answering:
```
Input: "What is the best thing about Kaggle?"
Output: "The best thing about Kaggle is the community. I have been a member of Kaggle for a while now and I have seen the community grow and evolve. The community is made up of people from all over the world who are passionate"
```

2. Text Generation:
```
Input: "Hello, my cat is cute"
Output: "Hello, my cat is cute and cuddly, but she is also a bit of a diva. She likes to be the center of attention, and she will do anything to get it."
```

## Contact

For any questions or suggestions, please contact:
- Email: ypssefmohammedahmed@gmail.com
- Phone: 01126078938
- GitHub: [Yossefmohammed](https://github.com/Yossefmohammed)

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Hugging Face Transformers library
- Google's Gemma model team
- The open-source community
