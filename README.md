# Photo or Text to 3D Model Converter

A prototype that converts either a photo of a single object or a text prompt into a simple 3D model. This project demonstrates image preprocessing techniques and AI/ML libraries for 3D generation.

## Features

- Accept image input (.jpg/.png) or text prompt
- Extract objects from images with background removal
- Generate 3D models from text prompts using open-source models
- Output downloadable .stl or .obj files
- Visualize the generated 3D models

## Installation

1. Clone this repository:
```
git clone https://github.com/yourusername/photo-to-3d.git
cd photo-to-3d
```

2. Create and activate a virtual environment:
```
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install the required dependencies:
```
pip install -r requirements.txt
```

## Usage

Run the Streamlit app:
```
streamlit run app.py
```

This will open a web interface where you can:
- Upload an image or enter a text prompt
- Process the input to generate a 3D model
- Visualize and download the resulting 3D model

Alternatively, use the command line interface:
```
python main.py --input image.jpg --output model.stl --type image
python main.py --input "A small toy car" --output model.stl --type text
```

## Approach and Methodology

### Image to 3D Conversion

For image inputs, the process follows these steps:
1. Preprocess the image (resize, normalize)
2. Remove the background using the backgroundremover library
3. Generate a 3D model using TripoSR, a state-of-the-art model for 3D reconstruction
4. Convert the generated model to .stl or .obj format

### Text to 3D Conversion

For text prompts, the approach is:
1. Use the LGM-full model from Hugging Face to convert text to a 3D representation
2. Process the output into a standard 3D format (.stl or .obj)
3. Prepare the model for visualization and download

## Libraries Used

- **torch** and **torchvision**: For neural network operations
- **backgroundremover**: For removing image backgrounds
- **diffusers**: For accessing text-to-3D models
- **trimesh**: For 3D mesh processing and visualization
- **numpy**: For numerical operations
- **streamlit**: For the web interface

## Limitations and Future Work

- Currently supports basic 3D model generation
- Limited complexity in generated models
- Future work could include:
  - Improved texture mapping
  - Better detail preservation
  - Support for multiple objects in a single image

