# VLM Floorplan Locator

This project leverages Vision-Language Models (VLMs) to determine the location of a photograph within a building's floor plan and generate landmark-based walking directions to a specified destination. The outputs are designed to be useful for blind or visually impaired users by avoiding references to grid positions and using physical landmarks instead.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Repository Structure](#repository-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Notes](#notes)

---

## Project Overview

This repository contains:

1. Prompt templates for querying VLMs with a floor plan image, structured JSON metadata, and a query image.
2. Jupyter notebooks to process images and metadata, interact with a local VLM (via [Ollama](https://ollama.com/)), and analyze the VLM’s output.
3. Example configurations for evaluating the model’s ability to localize the image and give blind-friendly directions.

---

## Repository Structure

```
vlm-floorplan-locator/
├── extracting_image_data_prompt.txt # Prompt template for VLM-based metadata extraction
├── floorplan_mask.ipynb # Optional notebook to manipulate floorplan layout or masks
├── images_to_text.ipynb # Converts images to text descriptions (node metadata)
├── main_queries.ipynb # Executes location + routing queries for each image
├── ollama_queries.ipynb # Demonstrates usage of VLM via Ollama API
├── prompt_with_floormap.txt # Main prompt template for location and navigation
```

---

## Prerequisites

- Python 3.8+
- Jupyter Notebook
- A local VLM server (e.g., [Ollama](https://ollama.com/)) with an image-capable model such as `llama3.2`.

Python packages:

```bash
pip install ollama tiktoken
```

Ollama setup:
```
ollama pull llava
```

## Installation
Clone this repository:
```
git clone https://github.com/shachafha/vlm-floorplan-locator.git
cd vlm-floorplan-locator
```


## Notes
* **Model Compatibility**
  This script assumes you have a local Ollama model that supports images (e.g. `llava`). If you want to use OpenAI’s API instead, refer to the original `locate_and_route.py` code in the OpenAI format.

* **Custom Destinations**
  You can modify the `DESTINATIONS` list to any text string (room number, “men’s restroom,” “cafeteria,” etc.). The prompt will replace `[DESTINATION]` accordingly.

---

Happy mapping! If you have questions or run into issues, feel free to open an issue in this repo.

