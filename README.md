# Materials Behavior Analyzer

An educational machine-learning project combining mechatronics and AI to classify material specimens using mechanical properties. A Streamlit dashboard runs predictions from a Random Forest classifier.

## Scope and limitations

The included dataset contains 30 labeled examples. Its source is not documented, and the training script fits all rows without a held-out evaluation. No accuracy or confidence score is reported. Predictions are a learning demonstration and are not validated for engineering safety decisions.

## Inputs and output

Inputs: material (Steel, Aluminum, Copper), yield strength (MPa), tensile strength (MPa), elongation (%), temperature (°C), test type (Tensile or Compression), and heat treatment (Yes or No).

The target is `Will_Fail`: 1 indicates likely failure and 0 indicates the non-failure class. The dashboard displays the predicted class; it does not calculate a confidence score or accept applied load as an input.

## Setup and run

Use Python 3.10 or later. Run commands from the project directory.

```bash
git clone https://github.com/Waelaladrysy/materials-behavior-analyzer.git
cd materials-behavior-analyzer
python -m venv .venv
```

Activate the environment:

- Windows PowerShell: `.venv\Scripts\Activate.ps1`
- macOS/Linux: `source .venv/bin/activate`

```bash
python -m pip install -r requirements.txt
python train_model.py
python -m streamlit run app.py
```

Training regenerates both model files with the installed library versions before the dashboard loads them. Retrain after changing the data or upgrading scikit-learn.

## Project structure

```text
.
├── app.py                      # Streamlit dashboard
├── train_model.py              # Training and artifact generation
├── material_data.csv           # 30 labeled examples
├── requirements.txt            # Python dependencies
├── material_failure_model.pkl  # Serialized classifier
├── label_encoders.pkl          # Categorical encoders
├── .gitignore
├── LICENSE
└── README.md
```

## Technologies

Python, pandas, NumPy, scikit-learn, joblib, and Streamlit.

## Developer

Wael Noman — Mechatronics Engineering graduate and M.Sc. student in Artificial Intelligence Engineering.

[GitHub profile](https://github.com/Waelaladrysy) · [LinkedIn](https://www.linkedin.com/in/wail-noman)

## License

[MIT](LICENSE)
