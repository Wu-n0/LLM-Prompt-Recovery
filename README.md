# README for LLM Prompt Recovery with Mistral 7B

This project focuses on recovering the prompts used to rewrite text using a large language model (LLM). It leverages the Mistral 7B model in conjunction with fine-tuning and a chat-based approach to predict the prompt that was most likely used to transform an original text into a rewritten version.

## Key Components

1. **Data Loading and Preparation**
   
    - **Data:** Employs the "llm-prompt-recovery" dataset, including original texts, rewritten versions, and the corresponding prompts used for the rewrites.
   
    - **Examples:** Utilizes a set of predefined example sequences to demonstrate the expected input/output format to the model.

2. **Model Selection and Optimization**
   
    - **Model:** Utilizes the Mistral 7B LLM, known for its capabilities in natural language understanding and generation.
   
    - **Quantization:** Applies 4-bit quantization to the model using BitsAndBytesConfig, allowing for efficient inference on GPU resources.
   
    - **Chat Template:** Structures the input to the model as a chat-style conversation to facilitate context understanding.

3. **Prompt Generation**
   
    - **Input:** Takes the original text and its rewritten version as input.
   
    - **Prompt Construction:** Crafts a prompt based on the examples and the specific text pair.
   
    - **Inference:** Executes the model to generate a predicted prompt based on the provided input.
   
    - **Post-processing:** Trims and cleans the generated prompt, removing numbered lists and extraneous text.

4. **Evaluation and Refinement**
   
    - **Baseline:** Incorporates a baseline prompt to use as a default if the generated prompt is too short or seems irrelevant.
   
    - **Example Testing:** Tests the model on a subset of the example data to showcase its predictions and estimate inference time.

5. **Submission**
   
    - **Inference on Test Data:** Processes the test dataset, generating prompts for each pair of original and rewritten text.
   
    - **Submission Formatting:** Formats the predictions into a CSV file according to the competition requirements.

## Additional Notes

- **Prompt Engineering:** The project heavily relies on crafting effective prompts to guide the model towards accurate predictions.
   
- **Memory Optimization:** Employs techniques like 4-bit quantization and limiting the number of new tokens generated to optimize GPU memory usage.
