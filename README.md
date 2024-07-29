# RDF_Extractor_Llama3

`RDF_Extractor_Llama3` is a Python-based tool that uses a language model to extract and summarize RDF (Resource Description Framework) data. This tool leverages the `langchain` library, the `Ollama` tool, and the Llama3 model (meta-llama/Meta-Llama-3-8B) to parse RDF files and format the extracted triplets.

## Overview

This project demonstrates how to configure and use a language model to process RDF data, extract meaningful information, and present it in a structured format. The RDF data in this example uses the FOAF (Friend of a Friend) vocabulary to describe people and their characteristics.

## Features

- Load RDF data from a specified file path.
- Initialize and configure the Ollama language model.
- Parse RDF data and extract triplets.
- Format and print the extracted information.

## Installation

To use this project, you'll need to set up a Python environment with the necessary dependencies and install Ollama and the required model. Follow these steps:

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
    - Run the following command to download the Llama3 (meta-llama/Meta-Llama-3-8B) model:
      ```bash
      ollama run llama3.1
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
   - Execute the Python script to generate RDF triplets from the provided RDF data file.

### Example of Prompt

   Please parse and extract RDF-like triplets from the text. For each identified triplet:
   1. Extracted_RDF_Set: (Subject, Predicate, Object)
   2. Identify the subject, predicate, and object.
   3. Format the output as RDF triplets with appropriate URIs and literals.
   4. Handle various types of information, including names, locations, dates, and numerical values.

   Use the following guidelines:
   - Format the output as follows for each triplet:
     **Triplet N**
     - Extracted_RDF_Set: (Subject, Predicate, Object)
     - Subject: [URL or Literal]
     - Predicate: [URL]
     - Object: [URL or Literal]

   Ensure to handle dates and numbers appropriately as literals or values in the RDF output.
   """


### Model Output Sample
**Triplet 1**
- Extracted_RDF_Set: (Barack Hussein Obama II, was born in, Honolulu)
- Subject: http://example.org/person/BarackObama
- Predicate: http://xmlns.com/foaf/0.1/birthPlace
- Object: http://example.org/location/Honolulu

**Triplet 2**
- Extracted_RDF_Set: (Barack Hussein Obama II, graduated from, Columbia University)
- Subject: http://example.org/person/BarackObama
- Predicate: http://xmlns.com/foaf/0.1/alumniOf
- Object: http://example.org/university/ColumbiaUniversity

**Triplet 3**
- Extracted_RDF_Set: (Barack Hussein Obama II, graduated in, 1983)
- Subject: http://example.org/person/BarackObama
- Predicate: http://example.org/ontology/graduationYear
- Object: "1983"

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your changes.

## Acknowledgements

This project uses the LangChain library and the Ollama LLM tool. Additionally, it incorporates the Llama3 model with the name meta-llama/Meta-Llama-3-8B.
