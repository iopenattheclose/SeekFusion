# SeekFusion

# SeekFusion AI - Understand Your Documents Better

## What it Does

SeekFusion AI is a simple tool I built to help you get answers from your PDF documents. Just upload a PDF, and you can ask it questions. It tries to understand what you're asking and gives you a short answer based on the text in the document.

## How it Works

Under the hood, it uses some clever stuff:

* It reads your PDF.
* It breaks the text into smaller pieces.
* It remembers what the text is about.
* When you ask a question, it finds the relevant parts of the document.
* Then, it uses a smart program running on my computer to give you an answer.

## Getting Started

### First Things First

1.  You need to have a program called Ollama installed. You can find it online. Make sure you also tell Ollama to get the `deepseek-r1:1.5b` model. Open your computer's command line and type:
    ```bash
    ollama pull deepseek-r1:1.5b
    ```
2.  You'll also need Python on your computer and a few extra helpers. Open your command line and type:
    ```bash
    pip install streamlit langchain-community langchain-text-splitters langchain-core langchain-ollama pdfplumber
    ```
3.  I need a place to put the PDFs you upload for a little while. So, if it's not there already, create a folder named `document_store` and inside that, another one named `pdfs`.

### Running the App

1.  Open your computer's command line.
2.  Go to the folder where you saved the Python code for SeekFusion AI.
3.  Type this and press Enter:
    ```bash
    streamlit run your_script_name.py
    ```
    (Make sure to replace `your_script_name.py` with the actual name of the file.)

4.  A web page should pop up in your browser. That's SeekFusion AI!


1.  You'll see a place to upload a PDF. Click "Browse files" and pick the PDF you want to ask about.
2.  Give it a moment to process the document. You'll see a message when it's done.
3.  At the bottom, there's a box where you can type your question. Just type what you want to know and press Enter.
4.  The answer from the document will show up on the screen.


In the code, there are some settings you can tweak if you're curious:

* `PDF_STORAGE_PATH`: Tells it where to save the PDFs temporarily (`document_store/pdfs/`).
* `EMBEDDING_MODEL`: The brain I use to understand the document (`deepseek-r1:1.5b`).
* `LANGUAGE_MODEL`: The bigger brain that helps me answer your questions (`deepseek-r1:1.5b`).
* `PROMPT_TEMPLATE`: The instructions I follow when trying to answer.
* `chunk_size`: How big the pieces of text are when I break down the document (currently around 1000 characters).
* `chunk_overlap`: How much the pieces of text overlap (currently around 200 characters).



