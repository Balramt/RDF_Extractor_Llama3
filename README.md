# RDF_Extractor_Llama3

`RDF_Extractor_Llama3`is a Python-based tool that uses a language model to extract and summarize RDF (Resource Description Framework) data. This tool leverages the `langchain` library, `Ollama` tool and LLama3 model (meta-llama/Meta-Llama-3-8B) to parse RDF files and format the extracted triplets.

## Overview

This project demonstrates how to configure and use a language model to process RDF data, extract meaningful information, and present it in a structured format. The RDF data in this example uses the FOAF (Friend of a Friend) vocabulary to describe people and their characteristics.

## Features

- Load RDF data from a specified file path.
- Initialize and configure the Ollama language model.
- Parse RDF data and extract triplets.
- Format and print the extracted information.

## Installation

To use this project, you'll need to set up a Python environment with the necessary dependencies, and install Ollama and the required model. Follow these steps:

### Step 1: Clone the Repository

```bash
git clone https://github.com/Balramt/RDF_Extractor_Llama3.git
cd RDF_Extractor_Llama3
```

### Step 2: Create a Virtual Environment

```bash
python -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
```

### Step 3: Install Required Python Packages

```bash
pip install langchain
```

### Step 4: Install Ollama

1. **Download and Install Ollama**:
    - Visit the [Ollama website](https://ollama.ai/) and follow the instructions to download and install Ollama for your operating system.
    
2. **Verify Installation**:
    - Ensure Ollama is installed correctly by running the following command:
      ```bash
      ollama --version
      ```

### Step 5: Download and Set Up the Llama3 Model

1. **Download the Llama3 Model**:
    - Run the following command to download the latest Llama3 model:
      ```bash
      ollama pull llama3:latest
      ```

2. **Verify Model Download**:
    - Ensure the model is downloaded correctly by listing the models:
      ```bash
      ollama models
      ```

## Usage

1. **Configure the Script**:
   - Update the `RDF_FILEPATH` variable with the path to your RDF file in the script.

2. **Run the Script**:
   - Open the Jupyter Notebook `RDF_Extractor.ipynb` in your preferred environment (e.g., Jupyter Lab or Jupyter Notebook).

### Example

Here's an example of how the script works:

1. **Configuration**:
   ```python
   LOCAL_MODEL = "llama3:latest"
   RDF_FILEPATH = r"D:\\New folder\\people.rdf"  # Update this with your RDF file path
   ```

2. **Initialize the Language Model**:
   ```python
   from langchain.llms import Ollama
   llm = Ollama(base_url="http://localhost:11434", model=LOCAL_MODEL, verbose=True)
   ```

3. **Extract and Format RDF Data**:
   ```python
   # Assume generated_text contains the output from the language model
   generated_text = """
   ... (model output here) ...
   """
   
   # Print generated summary
   print(f"Generated Summary:\n{generated_text}")
   ```

### Sample Output

The tool processes the RDF data and outputs the extracted triplets in a readable format. For instance:

```
Generated Summary:
Here are the triplets parsed from the RDF data, formatted according to your request:

**Triplet 1**
- Subject: http://example.org/person/1
- Predicate: http://xmlns.com/foaf/0.1/name
- Object: Alice

**Triplet 2**
- Subject: http://example.org/person/1
- Predicate: http://xmlns.com/foaf/0.1/age
- Object: 30

**Triplet 3**
- Subject: http://example.org/person/1
- Predicate: http://xmlns.com/foaf/0.1/mbox
- Object: mailto:alice@example.com

**Triplet 4**
- Subject: http://example.org/person/2
- Predicate: http://xmlns.com/foaf/0.1/name
- Object: Bob

**Triplet 5**
- Subject: http://example.org/person/2
- Predicate: http://xmlns.com/foaf/0.1/age
- Object: 25

**Triplet 6**
- Subject: http://example.org/person/2
- Predicate: http://xmlns.com/foaf/0.1/mbox
- Object: mailto:bob@example.com
```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your changes.

## Acknowledgements

This project uses the LangChain library and the Ollama LLM tool. Additionally, it incorporates the Llama3 model with the name meta-llama/Meta-Llama-3-8B
