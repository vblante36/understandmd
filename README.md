# UnderstandMD: Medical Terms Made Simple

UnderstandMD is a generative AI-powered tool that converts complex clinical medical descriptions into plain-language explanations understandable by a 12-year-old. It also supports audio output using text-to-speech, making medical information more accessible for all.

## Project Goal

Medical information is often filled with jargon that makes it hard for patients to understand. This project bridges that gap by using a locally hosted generative model to:

- Translate clinical descriptions into simplified explanations
- Identify common symptoms
- Convert the response to spoken audio

## Key Features

- **Offline model inference** using [Mistral-7B-Instruct](https://huggingface.co/mistralai/Mistral-7B-Instruct-v0.1) in GGUF format via `llama-cpp-python`
- **Fuzzy term matching** to support spelling errors or vague inputs
- **Text-to-speech** with `pyttsx3` (no API keys required)
- **Gradio UI** for easy interaction
- **Privacy-preserving & cost-free** – no cloud APIs used

## How It Works

1. **Input**: User enters a medical term and optionally a clinical description.
2. **LLM Processing**: The system generates a simplified explanation and common symptoms.
3. **Speech Output**: The explanation is converted to audio and played back.
4. **Interface**: A Gradio UI lets users interact in a friendly, accessible way.

## Example Output

| Medical Term | Simplified Explanation | Common Symptoms |
|--------------|------------------------|-----------------|
| Asthma       | Asthma makes it hard to breathe because the airways in your lungs can get tight and swollen. | Wheezing, coughing, shortness of breath, chest tightness |

## Tech Stack

- **Model**: Mistral-7B-Instruct (GGUF)
- **Local LLM Inference**: `llama-cpp-python`
- **Fuzzy Matching**: `rapidfuzz`
- **UI**: `Gradio`
- **TTS**: `pyttsx3` + `pydub`

## Setup Instructions

```bash
# Clone the repo
git clone https://github.com/your-username/understandmd.git
cd understandmd

# Create a virtual environment
python -m venv venv
source venv/bin/activate  # or .\venv\Scripts\activate on Windows

# Install dependencies
pip install -r requirements.txt

# Create a `.env` file and add your model path
echo "LLAMA_MODEL_PATH=/full/path/to/your/model.gguf" > .env

# Run the notebook or launch the UI
jupyter notebook  # OR run your main app script if applicable
```

understandmd/
├── models/                  # Local LLM model file (.gguf)
├── notebook.ipynb          # Project code and explanation
├── understandmd_generated.csv  # Output data (optional)
├── .env                    # Model path stored here
├── .gitignore
└── README.md

## Notes
	•	Requires a CPU capable of handling quantized LLM inference (e.g., Apple Silicon)
	•	Text-to-speech requires macOS-compatible audio handling due to use of .aiff files
	•	Model runs fully offline and never sends data to the cloud

## Future Directions
	•	Add multilingual support
	•	Improve output evaluation with real users
	•	Expand dataset coverage
	•	Enable mobile access or web deployment

## License

This project is for educational and non-commercial use only.

⸻

Built with 💙 by Victoria Blante
