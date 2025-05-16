# Civitai Model Downloader

Easily download one or multiple AI models from [Civitai](https://civitai.com/) directly to your machine or RunPod instance, with automatic filename detection, disk space checks, and robust error handling.

## Features

- Download single or multiple models via the Civitai API
- Keeps original filenames and extensions
- Handles network and file errors gracefully
- Logs progress and errors to both file and console
- Checks disk space before downloading
- Easy configuration of API key and save directory

## Requirements

- Python 3.7+
- Jupyter Notebook (or JupyterLab)
- [requests](https://pypi.org/project/requests/)
- [tqdm](https://pypi.org/project/tqdm/)

Install dependencies with:

```sh
pip install requests tqdm
```

## Usage

1. **Clone this repository** and open `civitai-downloader.ipynb` in Jupyter.
2. **Set your Civitai API key**  
   - Log in to [Civitai](https://civitai.com/)
   - Go to your profile settings and find your API key
   - Paste it in the appropriate cell in the notebook
3. **Add your model URLs**  
   - Copy the direct download links from Civitai (e.g., `https://civitai.com/api/download/models/123456`)
   - Add them to the `model_urls` list in the notebook
4. **Run the notebook cells**  
   - The models will be downloaded to your specified directory with progress bars and logs

## Example

```python
model_urls = [
    "https://civitai.com/api/download/models/638187",
    # Add more URLs as needed
]

downloaded_files = download_multiple_models(model_urls, api_key=os.environ["CIVITAI_API_KEY"], save_dir=SAVE_DIR)

print("\nDownloaded files:")
for f in downloaded_files:
    print(f)
```

## Notes

- The script checks for available disk space before downloading.
- All logs are saved to `civitai_download.log` and printed to the notebook output.
- Works on any machine with Python and Jupyter, including RunPod.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
