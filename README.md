## NPTEL-Nerd: Question Answering with Gemini for NPTEL Assignments

This repository provides a Streamlit web application that utilizes Google's Gemini family of Large Language Models (LLMs) to answer questions related to NPTEL assignments. Users can upload their assignment PDFs, ask questions about the content, and receive comprehensive answers with citations and reasoning directly from the uploaded documents.

### Overview

The application is built with Streamlit and leverages the Google Generative AI APIs for interaction with Gemini models. It allows users to upload assignments, ask questions via a chat interface, and receive responses based on the uploaded documents. The Gemini model is instructed to prioritize information from the uploaded files and only resort to its own knowledge when necessary.

### Features

* **Interactive User Interface:**  A user-friendly Streamlit interface for uploading files, asking questions, and receiving answers.
* **Document-Based Question Answering:** The Gemini model leverages the uploaded assignment PDFs as context to provide accurate and relevant answers.
* **Citation and Reasoning:**  Responses include citations and reasoning to indicate the source of the information within the uploaded documents.
* **Automated Cleanup:**  Uploaded files are automatically removed from Google Cloud storage after use, ensuring data privacy and security.

### Installation

1. **Install Python:** Ensure Python 3.7 or above is installed on your system.
2. **Create a Virtual Environment:**
   ```bash
   python3 -m venv venv-test
   source venv-test/bin/activate
   ```
3. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
4. **Set up Google Cloud Credentials:**
    * Follow the instructions in the [Google Cloud Generative AI documentation](https://cloud.google.com/generative-ai/docs/setup) to create a service account and obtain API credentials.
    * Set the environment variables `GOOGLE_APPLICATION_CREDENTIALS` to point to your service account's JSON key file.
5. **Run the Application:**
   ```bash
   streamlit run app.py
   ```

### Usage

1. **Open the application:** Access the Streamlit web application in your browser (usually `http://localhost:8501`).
2. **Upload your assignment:** Click the "Upload Assignment" button and select your PDF file.
3. **Ask your question:** Type your question in the chat interface and press Enter.
4. **Receive the answer:** The application will generate a response based on the uploaded document, providing citations and reasoning for the information.
5. **Repeat for more questions:**  Ask additional questions about the uploaded assignment.

### Code Breakdown

* **`app.py`:**
    * **`upload_to_gemini`:** Uploads assignment PDFs to Google Cloud storage.
    * **`cleanup_files`:**  Deletes uploaded files from Google Cloud storage.
    * **Streamlit components:**  Provides file upload, chat input, and response display functionalities.
    * **`genai.GenerativeModel`:**  Instantiates a Gemini model for text generation.
    * **`generate_content`:** Processes user queries and generates responses using the Gemini model and uploaded documents.
    * **Prompting:**  The prompt `sys_prpt` guides the Gemini model to prioritize information from the documents.
    * **Response formatting:** Responses include citations and reasoning to indicate the source of information.
* **`requirements.txt`:**
    * **`google-generativeai`:** Enables interaction with Google's Generative AI APIs.
    * **`protobuf`:**  Supports Protocol Buffers for data serialization.
    * **`streamlit`:**  The library for building the Streamlit web application.

### Contribution Guidelines

Contributions are welcome! Feel free to open issues or submit pull requests. 

Please follow these guidelines:

* **Fork the repository:** Create a fork of the repository on your GitHub account.
* **Create a branch:** Create a new branch from the `main` branch for your changes.
* **Make your changes:** Implement your feature or fix the bug.
* **Commit your changes:** Commit your changes with a descriptive message.
* **Push your changes:** Push your branch to your forked repository.
* **Open a pull request:** Open a pull request on the original repository, requesting to merge your changes into the `main` branch.

### License

This project is licensed under the [MIT License](LICENSE).

### Acknowledgments

* Google for providing the Gemini family of LLMs and the Generative AI APIs.
* The Streamlit team for creating a user-friendly framework for web application development.

### Disclaimer

This project is for educational and research purposes only. It should not be used for any commercial or illegal activities. The authors are not responsible for any misuse or damages caused by this project. 

