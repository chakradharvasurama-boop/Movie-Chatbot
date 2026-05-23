# IMDb Movie Chatbot

This project is a movie recommendation and question-answering chatbot built on top of an IMDb dataset. It combines structured filtering with semantic search so users can ask for recommendations, movie details, ratings, genres, cast information, and follow-up questions in a conversational way.

## What It Does

- Loads and prepares an IMDb movie dataset
- Builds rich movie descriptions from title, genre, year, rating, director, cast, and duration
- Creates embeddings and stores them in a FAISS vector index
- Uses LangChain and OpenAI models to answer movie-related questions
- Supports exact filtering by fields like genre, year, actor, director, and minimum rating
- Supports semantic search for fuzzy requests such as "movies like Interstellar"
- Exposes the chatbot through a Gradio interface

## Tech Stack

- Python
- Pandas
- OpenAI
- LangChain
- FAISS
- Gradio

## Project Files

- `Chakradhar_Reddy_Yerragudi_IMDB_Movie_Chatbot.ipynb`: main notebook containing data prep, retrieval pipeline, chatbot logic, and Gradio UI
- `IMDb_Dataset.csv`: source movie dataset used by the chatbot

## Setup

Install the main dependencies used in the notebook:

```bash
pip install pandas openai gradio faiss-cpu langchain langchain-openai langchain-community langchain-text-splitters langchainhub
```

Set your OpenAI API key before running the notebook:

```bash
export OPENAI_API_KEY="your_api_key_here"
```

## How To Run

1. Open `Chakradhar_Reddy_Yerragudi_IMDB_Movie_Chatbot.ipynb` in Jupyter Notebook or JupyterLab.
2. Run the cells in order to:
   - load the dataset
   - create movie descriptions
   - build embeddings and the FAISS index
   - initialize the chatbot chain
   - launch the Gradio interface
3. Use the Gradio UI to ask questions such as:
   - `Recommend good sci-fi movies`
   - `Show action movies after 2015 with rating above 8`
   - `Who directed Inception?`
   - `Suggest movies like Interstellar`

## Notes

- The notebook currently reads the CSV from a local absolute path. If needed, update that cell to use a relative path like `IMDb_Dataset.csv`.
- The chatbot is designed around the local dataset, so answers depend on the movies available in the CSV.

## Future Improvements

- Add web search for newer movie information outside the dataset
- Improve the UI with posters and richer result cards
- Move the notebook workflow into a standalone Python app
