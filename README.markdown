# Resume-to-Job-Description Matching with Sentence-BERT

## Overview
This project implements a resume-to-job-description matching system using the Sentence-BERT (`all-MiniLM-L6-v2`) model. It extracts text from resumes in PDF format, cleans the text, and computes cosine similarity scores between resume embeddings and job description embeddings to rank job descriptions based on their relevance to a given resume.

The system is designed to help job seekers identify the most suitable job opportunities by matching their resumes to job descriptions based on semantic similarity.

## Features
- **PDF Text Extraction**: Extracts text from resume PDFs using PyMuPDF.
- **Text Cleaning**: Processes extracted text to remove noise and irrelevant content (requires a `clean_resume` function, not included in the provided code).
- **Semantic Matching**: Uses Sentence-BERT to encode resumes and job descriptions into embeddings and computes cosine similarity for matching.
- **Ranking**: Ranks job descriptions by similarity scores to identify the best matches for a resume.

## Requirements
- Python 3.6+
- Libraries:
  - `pymupdf` (for PDF text extraction)
  - `sentence-transformers` (for Sentence-BERT model)
  - `scikit-learn` (for cosine similarity computation)
  - `numpy` (for numerical operations)

## Installation
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/resume-job-matching.git
   cd resume-job-matching
   ```

2. **Set Up a Virtual Environment** (optional but recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Dependencies**:
   ```bash
   pip install pymupdf sentence-transformers scikit-learn numpy
   ```

## Usage
1. **Prepare Your Resume**:
   - Place your resume in PDF format (e.g., `RESUME.pdf`) in the project directory.

2. **Run the Matching Script**:
   - The main script (`Resume_job_matching_using_BERT.ipynb`) includes the following steps:
     - Extract text from the resume PDF.
     - Clean the extracted text (you need to provide or implement the `clean_resume` function).
     - Encode the resume and job descriptions using Sentence-BERT.
     - Compute cosine similarity scores and rank job descriptions.
   - Example job descriptions are hardcoded in the script:
     ```python
     job_descriptions = [
         "Looking for a data analyst with Python, SQL, and data visualization experience.",
         "Seeking a machine learning engineer with experience in deep learning and PyTorch.",
         "We need a web developer skilled in HTML, CSS, JavaScript, and React."
     ]
     ```

3. **Run the Notebook**:
   - Open the Jupyter Notebook:
     ```bash
     jupyter notebook Resume_job_matching_using_BERT.ipynb
     ```
   - Execute the cells sequentially to process your resume and display the ranked job description matches.

4. **Example Output**:
   ```plaintext
   JD 2: Score = 0.3171 | Seeking a machine learning engineer with experience in deep learning and PyTorch.
   JD 1: Score = 0.2214 | Looking for a data analyst with Python, SQL, and data visualization experience.
   JD 3: Score = 0.1851 | We need a web developer skilled in HTML, CSS, JavaScript, and React.
   ```

## Project Structure
```
resume-job-matching/
│
├── Resume_job_matching_using_BERT.ipynb  # Main Jupyter Notebook
├── RESUME.pdf                            # Input resume (not included)
├── README.md                             # This file
└── requirements.txt                      # Dependency list (optional)
```

## Notes
- **Text Cleaning**: The provided code references a `clean_resume` function, which is not included. You must implement this function to preprocess the resume text (e.g., remove special characters, normalize text).
- **Job Descriptions**: The example uses three hardcoded job descriptions. To extend the system, you can load job descriptions from a file or database.
- **Scalability**: For large-scale matching, consider batch processing resumes and job descriptions to improve performance.
- **GPU Support**: The notebook is configured to use a GPU (e.g., T4 in Colab). Ensure your environment supports GPU acceleration for faster encoding with Sentence-BERT.

## Future Improvements
- Implement the `clean_resume` function for robust text preprocessing.
- Add support for loading multiple resumes and job descriptions from a dataset.
- Integrate a database or API to fetch job descriptions dynamically.
- Enhance the matching algorithm with additional features (e.g., keyword extraction, weighted scoring).
- Add a user interface for easier interaction (e.g., a web app using Flask or Streamlit).

## Contributing
Contributions are welcome! Please fork the repository and submit a pull request with your changes. Ensure your code follows PEP 8 guidelines and includes appropriate documentation.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact
For questions or suggestions, feel free to open an issue on GitHub or contact [your-email@example.com](mailto:your-email@example.com).