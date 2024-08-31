# PlantSy ML and API Repository

This repository contains the machine learning models, notebooks, and API deployment files for the PlantSy Android application.

## Repository Structure

```
plantsy-ml-api/
├── notebooks/
│   ├── cnn_plant_disease_detection.ipynb
│   └── lstm_text_classification.ipynb
├── models/
│   ├── plant_disease_model.h5
│   └── text_classification_model.h5
├── api/
│   ├── main.py
│   ├── requirements.txt
│   └── Dockerfile
└── README.md
```

## Contents

1. **Notebooks**: Jupyter notebooks used for model development and training.
   - `cnn_plant_disease_detection.ipynb`: CNN model for plant disease detection
   - `lstm_text_classification.ipynb`: LSTM model for filtering community conversations

2. **Models**: Exported model files ready for deployment.
   - `plant_disease_model.h5`: Trained CNN model for plant disease detection
   - `text_classification_model.h5`: Trained LSTM model for text classification

3. **API**: FastAPI implementation for model serving.
   - `main.py`: Main FastAPI application
   - `requirements.txt`: Python dependencies
   - `Dockerfile`: For containerizing the API

## Setup and Installation

1. Clone the repository:
   ```
   git clone https://github.com/yourusername/plantsy-ml-api.git
   cd plantsy-ml-api
   ```

2. Set up a Python virtual environment:
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
   ```

3. Install the required packages:
   ```
   pip install -r api/requirements.txt
   ```

4. For running notebooks, install Jupyter:
   ```
   pip install jupyter
   ```

## Usage

### Running Notebooks

Navigate to the `notebooks/` directory and start Jupyter:

```
cd notebooks
jupyter notebook
```

### API Deployment

1. Navigate to the `api/` directory:
   ```
   cd api
   ```

2. Run the FastAPI application:
   ```
   uvicorn main:app --reload
   ```

   The API will be available at `http://localhost:8000`.

3. For Docker deployment:
   ```
   docker build -t plantsy-api .
   docker run -p 8000:8000 plantsy-api
   ```

## API Documentation

Once the API is running, you can access the auto-generated Swagger documentation at `http://localhost:8000/docs`.

## Model Details

### Plant Disease Detection (CNN)

- Input: 224x224 RGB image
- Output: Disease classification (list of supported diseases in `api/main.py`)

### Text Classification (LSTM)

- Input: Text string
- Output: Binary classification (plant-related or not)

## Contributing

We welcome contributions to improve our models and API! Please read our [Contributing Guidelines](CONTRIBUTING.md) before submitting pull requests.

## License

This project is licensed under the GNU General Public License v2.0 - see the [LICENSE](LICENSE) file for details.

## Contact

For any queries regarding this ML and API repository, please open an issue on GitHub or contact us at ml-support@plantsy.com.
