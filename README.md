# Alt Text Generator

## Overview
The Alt Text Generator is a Python application that processes images to generate descriptive alt text using OpenAI's GPT-4o model with vision capabilities. It reads images from a specified folder, resizes them, and sends them to the OpenAI API for alt text generation.

## Features
- Processes multiple image formats (PNG, JPG, JPEG, WEBP, GIF, AVIF).
- Resizes images to specified dimensions.
- Generates alt text for each image using the OpenAI API.
- Saves resized images to the `/tmp` directory.
- Outputs a CSV report containing the image names, sizes, and generated alt text.

## Requirements
- Python 3.7 or higher
- `requests` library
- `Pillow` library
- `pillow-avif-plugin` (for AVIF support)

## Installation
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd alt-text-generator
   ```

2. Install the required packages:
   ```bash
   pip install requests Pillow pillow-avif-plugin
   ```

## Configuration
- Set your OpenAI API key in the script by replacing the placeholder in the `API_KEY` variable.
- Specify the folder path containing the images you want to process by updating the `FOLDER_PATH` variable.

## Usage
1. Run the application:
   ```bash
   python alt-tester.py
   ```

2. The application will process all images in the specified folder, resize them, and generate alt text.

3. Check the generated CSV report (`alt_text_report.csv`) for the results, which includes:
   - Image name
   - Size of the resized image
   - Generated alt text or "error" if the request failed

## Error Handling
- The application retries failed requests up to three times, waiting one second between attempts.
- If an error occurs during processing, it logs the error and continues with the next image.
