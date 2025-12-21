# game-metr-analyzer
[![PyPI version](https://badge.fury.io/py/game-metr-analyzer.svg)](https://badge.fury.io/py/game-metr-analyzer)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![Downloads](https://static.pepy.tech/badge/game-metr-analyzer)](https://pepy.tech/project/game-metr-analyzer)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-blue)](https://www.linkedin.com/in/eugene-evstafev-716669181/)


A Python package to analyze and interpret game narratives or story structures, focusing on the METR (Mechanics, Esthetics, Technology, and Rhetoric) plot framework used in game design. It processes textual descriptions of game plots, mechanics, or player experiences and returns a structured breakdown of these elements. This helps game developers, critics, and educators systematically evaluate and enhance game narratives without subjective bias.

## Installation

Install the package via pip:

```bash
pip install game_metr_analyzer
```

## Usage

Import and use the main function as shown:

```python
from game_metr_analyzer import game_metr_analyzer

response = game_metr_analyzer(
    user_input="Your game plot description here",
    # Optional: specify a custom LLM instance
    # llm=your_llm_instance,
    # Optional: specify API key for LLM7
    # api_key="your_api_key"
)
```

## Parameters

- `user_input` (str): The textual description of the game plot, mechanics, or player experience to analyze.
- `llm` (Optional[BaseChatModel]): An instance of a language model (e.g., from langchain). If not provided, the default `ChatLLM7` will be used.
- `api_key` (Optional[str]): The API key for `ChatLLM7`. If not provided, it will be read from the environment variable `LLM7_API_KEY`.

## Supported Language Models

This package uses `ChatLLM7` from `langchain_llm7` by default. You can pass your own language model instance to utilize other services such as:

- OpenAI's models:
  ```python
  from langchain_openai import ChatOpenAI
  
  llm = ChatOpenAI()
  response = game_metr_analyzer(user_input, llm=llm)
  ```

- Anthropic:
  ```python
  from langchain_anthropic import ChatAnthropic
  
  llm = ChatAnthropic()
  response = game_metr_analyzer(user_input, llm=llm)
  ```

- Google Generative AI:
  ```python
  from langchain_google_genai import ChatGoogleGenerativeAI

  llm = ChatGoogleGenerativeAI()
  response = game_metr_analyzer(user_input, llm=llm)
  ```

## API Key Management

The default rate limits for `ChatLLM7` are sufficient for most use cases. To access higher limits:

- Set the `LLM7_API_KEY` environment variable:
  ```bash
  export LLM7_API_KEY="your_api_key"
  ```
- Or pass it directly:
  ```python
  response = game_metr_analyzer(user_input, api_key="your_api_key")
  ```

You can obtain a free API key by registering at [https://token.llm7.io/](https://token.llm7.io/).

## License

This project is licensed under the MIT License.

## Author

- Eugene Evstafev
- Email: hi@eugene.plus

## GitHub

- [https://github.com/chigwell](https://github.com/chigwell)

## Issues

For bugs or feature requests, please use the GitHub issues page: [https://github.com/...](https://github.com/...)