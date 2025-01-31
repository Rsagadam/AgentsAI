# Image Generation with Smolagents
This repository demonstrates how to generate images using the smolagents library and the FLUX.1-schnell model. By providing a textual description, the model generates images that match the prompt.

# Requirements
Before you begin, ensure you have the following installed:

Python 3.x
smolagents
Pillow (for image manipulation)
urllib (for downloading the generated image)
Installation
To install the required libraries, run:

bash
Copy
pip install smolagents Pillow
Usage
1. Import Necessary Libraries
Start by importing the required libraries in your Python script:

python
Copy
from smolagents import Tool
from urllib.request import urlretrieve
from PIL import Image
2. Set Up the Image Generation Tool
The smolagents library provides tools that allow you to generate images based on a text prompt. The following code initializes the FLUX.1-schnell model for image generation:

python
Copy
image_generation_tool = Tool.from_space(
    "black-forest-labs/FLUX.1-schnell", 
    name="image_generator", 
    description="Generate an image from a prompt"
)
3. Generate an Image from a Prompt
Now, provide a prompt for the image generation tool. For example, to generate an image of a beautiful brown lady in an aesthetic Indian background, use the following code:

python
Copy
x = image_generation_tool("a beautiful brown lady in aesthetic Indian background, temples and flowers")
The x variable will contain the URL of the generated image.

4. Download and Display the Image
To download and display the generated image, you can use the Pillow library. The following code downloads the image and opens it in the default viewer:

python
Copy
# Assuming 'x' contains the URL of the generated image
image_url = x

# Download the image
urlretrieve(image_url, "generated_image.jpg")

# Open and display the image
background = Image.open("generated_image.jpg")
background.show()
This will show the image in a pop-up viewer, allowing you to view the result of the generated image.

# Example Prompt
Here is an example of a descriptive text prompt that you can use:

css
Copy
"a beautiful brown lady in an aesthetic Indian background, temples, and flowers"
Model Details
The model used for generating the image is FLUX.1-schnell, which is hosted by Black Forest Labs. The model generates an image based on your textual input, so the more detailed and specific your prompt, the better the result.

# License
This project is licensed under the MIT License - see the LICENSE file for details.
