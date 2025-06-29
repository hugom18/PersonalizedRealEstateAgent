# HomeMatch: Personalized Real Estate Agent

## Project Overview

HomeMatch is an application that uses a Large Language Model and a vector database to create property descriptions tailored to buyer preferences.

It follows these steps:

1. Synthetic data generation: generate at least ten realistic property listings with an LLM and save them as JSON and text files
2. Vector indexing: compute embeddings for each listing and store them in ChromaDB
3. Semantic search: embed free-form buyer preferences and retrieve the most similar listings by vector similarity
4. Description personalization: use an LLM prompt to rewrite each matched listing, emphasizing buyer priorities without changing facts
5. Interactive demo: prompt the user for preferences and display the top personalized listings

*Optional enhancement:* add image-based search by embedding property photos and combining text and image similarity.

## Features and Rubric Alignment

1. **Synthetic data generation:** implemented in the generate\_listings function, saved to listings.json and listings.txt
2. **Vector database and storage:** set up ChromaDB and added embeddings via collection.add
3. **Semantic search:** defined search\_listings to return top-k matches for a given preference string
4. **Search and personalization flow:** for each search result, call personalize\_listing to generate tailored descriptions
5. **LLM-based personalization:** implemented with a prompt template and LangChain’s LLMChain

## Setup and Installation

1. Create and activate a virtual environment:

   python -m venv venv    # create
   source venv/bin/activate   # macOS/Linux
   venv\Scripts\activate     # Windows

2. Install dependencies:

   pip install -r requirements.txt

3. Set environment variables:

   export OPENAI\_API\_KEY="\<YOUR\_OPENAI\_KEY>"
   export OPENAI\_API\_BASE="(https://openai.vocareum.com/v1)""

## Usage

1. Open the main notebook:

   jupyter notebook HomeMatch.ipynb

2. Run the cells in sequence for setup, data generation, indexing, search, personalization, and demo.

## File layout

* HomeMatch.ipynb: main notebook
* listings.json: generated listings in JSON
* listings: listings in line-delimited JSON
* requirements.txt: dependency list
* README.md: this file

## Project Documentation

The notebook starts with a documentation section that recaps each step, explains how to run the code, and lists all deliverables.
