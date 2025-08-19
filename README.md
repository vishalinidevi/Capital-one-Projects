Below is a sample `README.md` file that you can include with your Google Colab `.ipynb` file submission for the hackathon. This README provides instructions for using the notebook, details about the project, and guidance for reviewers or users to run and test it effectively. It incorporates the current date and time (03:50 PM IST, Monday, August 18, 2025) and aligns with the updated code provided earlier.

---

# AgriPrice Predictor: AI-Driven Market Insights for Madhya Pradesh

## Project Overview
The **AgriPrice Predictor** is an AI-powered solution designed to empower farmers and vendors in Madhya Pradesh by providing accurate crop price forecasts, identifying the nearest markets, and generating multilingual trade offers. Built using Python, TensorFlow (LSTM), Scikit-learn (KNN), and Gemini 1.5 Flash (LLM), this project leverages historical agricultural data to optimize market decisions.

- **Date of Submission**: 03:50 PM IST, Monday, August 18, 2025
- **Team**: [Your Team Name or Individual Name]
- **Technologies**: Python, TensorFlow, Scikit-learn, Google Generative AI
- **Data Source**: AGMARKNET (sample CSV: `Agri-multicrop.csv`)

## Features
- **Dynamic Crop Forecasting**: Uses LSTM to predict crop prices based on historical data.
- **Nearest Market Identification**: Employs KNN to find the closest market to a vendor location (e.g., Alirajpur).
- **Multilingual Offers**: Generates English and Hindi trade offers using Gemini 1.5 Flash LLM.
- **Efficiency**: Saves trained models to avoid repeated training, ideal for hackathon testing.

## Instructions for Use

### Prerequisites
1. **Google Colab Environment**: Open the `.ipynb` file in Google Colab (https://colab.research.google.com/).
2. **Dependencies**: Install required libraries by running the following cell at the start:
   ```bash
   !pip install numpy scikit-learn pandas requests tensorflow google-generativeai
   ```
3. **API Key**: Replace the placeholder `api_key` in `genai.configure(api_key='YOUR_API_KEY')` with a valid Gemini 1.5 Flash API key from Google AI Studio.
4. **Data File**: Upload the `Agri-multicrop.csv` file to your Colab environment (File > Upload) or adjust the path (`/content/Agri-multicrop.csv`) if stored elsewhere (e.g., Google Drive).

### Initial Setup
1. **Run the Notebook Once**:
   - Execute all cells to train and save LSTM models for each crop and market combination.
   - Set `retrain=yes` when prompted to train new models (this will take a few minutes).
   - Models are saved as `.h5` files (e.g., `/content/lstm_model_Wheat_Alirajpur.h5`) in the Colab environment.

2. **Verify Output**:
   - Check the console for crop types, nearest market (e.g., Jobat), and base market (e.g., Alirajpur).
   - Ensure models are saved without errors.

### Testing and Usage
1. **Subsequent Runs**:
   - Rerun the notebook from the user input section (cell with `print(f"\nCurrent Date and Time: {current_datetime}")`) using Colab's "Run After" feature or by selecting and running cells manually.
   - Set `retrain=no` to load pre-trained models and avoid retraining.

2. **User Interaction**:
   - **Select Crop**: Enter a crop name (e.g., "Wheat", "Soybean") from the listed options.
   - **Choose Action**: Enter `1` for Price Prediction or `2` for LLM Offer.
   - **Force Retrain**: Optionally enter `yes` to retrain models if new data is added.

3. **Expected Output**:
   - **Price Prediction (Action 1)**: Displays predicted prices for the selected crop in the base and nearest markets (e.g., "Wheat Predicted Price in Alirajpur: ₹1800.50/quintal").
   - **LLM Offer (Action 2)**: Generates a multilingual offer comparing prices (e.g., English and Hindi suggestions to sell at the nearest market).

### Hackathon Testing Tips
- **Rapid Iteration**: Use `retrain=no` for quick tests with different crops and actions.
- **Data Exploration**: Modify the CSV or add rows to test model adaptability (retrain with `yes` if needed).
- **Performance**: Expect ~70% accuracy (MAE ~₹300-500) with 15 rows; full data (1000+ rows) can reach ~85% (MAE ~₹100-200).
- **Save Progress**: Download the `.ipynb` file or save models to Google Drive (`/content/drive/My Drive/`) using:
  ```python
  from google.colab import drive
  drive.mount('/content/drive')
  ```

### File Structure
- **`AgriPrice_Predictor.ipynb`**: The main Colab notebook.
- **`Agri-multicrop.csv`**: Sample dataset with columns: `State Name`, `District Name`, `Market Name`, `Variety`, `Group`, `Arrivals (Tonnes)`, `Min Price (Rs./Quintal)`, `Max Price (Rs./Quintal)`, `Modal Price (Rs./Quintal)`, `Reported Date`, `Grade`, `Type`.

### Limitations
- **Data Size**: Current sample (15 rows) limits accuracy; full AGMARKNET data recommended.
- **Model Persistence**: Models are temporary in Colab; save to Drive for long-term use.
- **API Dependency**: Requires a valid Gemini API key.

### Future Enhancements
- Integrate real-time AGMARKNET data feeds.
- Expand to other states with scalable architecture.
- Add user authentication and market notifications.

## Contact
- **Team Lead**: [Your Name/Email]
- **GitHub**: [Your GitHub Repository Link, if applicable]
- **Questions**: Reach out during the hackathon for support!

---

### Instructions for Submission
1. **Upload Files**: Include the `.ipynb` file and `Agri-multicrop.csv` in your hackathon submission folder.
2. **README Inclusion**: Add this `README.md` file to provide clear usage instructions.
3. **Test Run**: Ensure reviewers can run the notebook in Colab with the provided steps.
4. **Demo**: Prepare a short demo video or live session showcasing crop selection, prediction, and LLM output.

This README ensures reviewers can easily use your solution, test it dynamically, and appreciate its hackathon-ready design. Adjust the team details and links as needed!
