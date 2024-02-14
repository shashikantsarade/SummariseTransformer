import streamlit as st
from transformers import pipeline

# Load the summarization pipeline
summarizer = pipeline("summarization")

def summarize_text(text):
    """Summarizes the provided text using the loaded summarization pipeline.

    Args:
        text (str): The text to be summarized.

    Returns:
        str: The summarized text.
    """

    try:
        summary = summarizer(text, max_length=200, num_beams=4, early_stopping=True)  # Customize parameters as needed
        return summary[0]["summary_text"]
    except Exception as e:
        st.error(f"An error occurred: {e}")
        return "Error summarizing the text."

def main():
    """Creates a Streamlit app for text summarization."""

    st.title("Text Summarizer")
    st.markdown("Enter the text you want to summarize below:")

    text_input = st.text_area("", height=200)

    if st.button("Summarize"):
        summary = summarize_text(text_input)
        st.success("Summary:")
        st.markdown(summary)

if __name__ == "__main__":
    main()
