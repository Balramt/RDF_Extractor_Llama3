# RDF Triplet Extraction Using Llama3

This project demonstrates how to use the `langchain` library with the Llama3 model to extract RDF triplets from a text file. The script reads RDF data from a specified text file, constructs a prompt to parse and extract RDF-like triplets, and outputs the results in a specified format.

## Prerequisites

- Python 3.x
- `langchain` library
- A running instance of the Llama3 model server

## Installation

1. **Install Required Packages**

   Make sure you have the `langchain` library installed. You can install it using pip:

   ```bash
   pip install langchain
   ```

2. **Set Up Llama3 Model Server**

   Ensure that your Llama3 model server is running and accessible at `http://localhost:11434`.

## Usage

1. **Update File Path**

   Update the `RDF_FILEPATH` variable in the script to point to your text file containing the RDF data.

   ```python
   RDF_FILEPATH = r"D:\New folder\RDF_Extractor_Llama3\Barack-Obama.txt"
   ```

2. **Run the Script**

   Execute the Python script to generate RDF triplets from the text data.

   ```bash
   python your_script_name.py
   ```

## Script Details

The script performs the following actions:

1. **Read RDF Data**

   It reads the RDF data from a specified text file.

2. **Construct Prompt**

   It constructs a prompt for the Llama3 model, specifying how to parse and extract RDF-like triplets from the text. The prompt includes:

   - Identification of subject, predicate, and object.
   - Formatting guidelines for RDF triplets.
   - Examples for reference.

3. **Generate RDF Triplets**

   It sends the constructed prompt to the Llama3 model and generates RDF triplets.

4. **Print Results**

   It prints the generated RDF triplets.

## Example Prompt

The prompt provided to the model is as follows:

```
Here is the RDF data: 

{rdf_data}

Please parse and extract RDF-like triplets from the text. For each identified triplet:
1.Extracted_RDF_Set: (Subject, Predicate, Object)
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

Examples:
Text: "Obama was born in Honolulu, Hawaii. He graduated from Columbia University in 1983."

Outputs:
**Triplet 1**
- Extracted_RDF_Set: (Obama, was born in, Honolulu)
- Subject: http://example.org/person/BarackObama
- Predicate: http://xmlns.com/foaf/0.1/birthPlace
- Object: http://example.org/location/Honolulu

**Triplet 2**
- Extracted_RDF_Set: (Obama, graduated from, Columbia University)
- Subject: http://example.org/person/BarackObama
- Predicate: http://xmlns.com/foaf/0.1/alumniOf
- Object: http://example.org/university/ColumbiaUniversity

**Triplet 3**
- Extracted_RDF_Set: (Obama, graduated in, 1983)
- Subject: http://example.org/person/BarackObama
- Predicate: http://example.org/ontology/graduationYear
- Object: "1983"

Ensure to handle dates and numbers appropriately as literals or values in the RDF output.
```

## Notes

- Ensure the text file contains properly formatted RDF data for accurate extraction.
- Adjust the `max_length` parameter in the `llm.generate` method if necessary to accommodate larger RDF data.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.
