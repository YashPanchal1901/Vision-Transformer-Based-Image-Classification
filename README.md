

# **Vision-Transformer-Based-Image-Classification**

## Overview

This Streamlit application identifies food items from uploaded images and provides their nutritional information using a pre-trained ViT model for image classification and the API Ninjas Nutrition API for retrieving detailed nutrition data.

## Features
1. **Food Identification**:
   - Upload an image of a food item.
   - The app uses the `google/vit-base-patch16-224` Vision Transformer (ViT) model to classify the food item.

2. **Nutritional Information**:
   - The app retrieves nutritional information such as calories, fat, protein, and carbohydrates from the **API Ninjas Nutrition API**.
   - Displays the information in a formatted table.

3. **Try the Model**:
   - You can try the model [Project](vision-transformer-based-image-classification-pw44b9zyappdyhow.streamlit.app).

## Dependencies

Ensure the following Python libraries are installed:
- `streamlit`
- `Pillow`
- `transformers`
- `requests`

Install them using:
```bash
pip install -r requirements.txt
```

## File Structure
- **main.py**: The main script for the Streamlit app.
- **secrets.toml**: A configuration file storing the API key.

## Setup

1. **Install Python**: Use Python 3.8 or later.

2. **Install Dependencies**:
   Install the required libraries as mentioned above.

3. **API Key**:
   - Obtain an API key from [API Ninjas](https://api-ninjas.com/).
   - Save the key in your `.streamlit/secrets.toml` file:
     ```
     [secrets]
     Ninja_API = "your_api_key_here"
     ```

4. **Run the App**:
   Start the Streamlit application:
   ```bash
   streamlit run main.py
   ```

## How to Use

### Steps:
1. **Upload an Image**:
   - Click on the "Choose an image..." button and upload a food image (JPG format).
   - The uploaded image will be displayed on the app.

2. **Food Identification**:
   - The app identifies the food item using the Vision Transformer model.
   - Displays the predicted food item name.

3. **Retrieve Nutrition Info**:
   - Fetches detailed nutritional data for the identified food item using the API Ninjas Nutrition API.
   - Displays the information in a tabular format.

4. **Try the Model**:
   - Click the "Try ViT on Hugging Face" link to explore the ViT model directly on [Hugging Face](https://huggingface.co/google/vit-base-patch16-224).

## Code Snippet: Adding the Model Link
To add the "Try ViT on Hugging Face" feature, include this at the end of your script:
```python
st.write("### Want to explore the model?")
st.markdown("[Try ViT on Hugging Face](https://huggingface.co/google/vit-base-patch16-224)", unsafe_allow_html=True)
```

## Example Output

### Identified Food
- **Uploaded Image**: `Pizza.jpg`
- **Predicted Food Item**: Pizza

### Nutritional Table
| Metric                | Value       | Metric              | Value       |
|-----------------------|-------------|---------------------|-------------|
| Calories              | 250 kcal    | Serving Size (g)    | 100 g       |
| Total Fat (g)         | 9 g         | Saturated Fat (g)   | 3 g         |
| Protein (g)           | 11 g        | Sodium (mg)         | 600 mg      |
| Potassium (mg)        | 200 mg      | Cholesterol (mg)    | 30 mg       |
| Total Carbohydrates (g)| 30 g       | Fiber (g)           | 2 g         |
| Sugar (g)             | 4 g         |                     |             |

## Troubleshooting
1. **Image Not Identified**:
   - Ensure the uploaded image is clear and properly formatted (JPG only).
2. **Nutritional Information Missing**:
   - If no information is found, ensure the identified food item is specific and available in the API database.
3. **API Errors**:
   - Verify the API key in the `secrets.toml` file.
   - Check API limits if the app is heavily used.

## License
Distributed under the MIT License.
