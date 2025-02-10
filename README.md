# YouTube AI Summary

This Python script converts YouTube video transcripts into well-structured summarized posts using a local llm . It automates the process of fetching video details, extracting transcripts, and summarizing the content.

## Features

- Fetches YouTube video title and transcript.
- Summarizes transcript i.
- Saves the generated content as a Markdown (`.md`) file.
- Supports local use with Ollama's AI reasoning models, such as `deepseek-r1`.

## Prerequisites

- Python 3.8+
- [Ollama](https://ollama.com/) installed locally.
- YouTube Transcript API: `youtube-transcript-api`
- PyTubeFix: `pytubefix`
- Ollama Python SDK: `ollama`

## Installation

1. Clone this repository or copy the script.
2. Install the required dependencies:
   ```bash
   pip install youtube-transcript-api pytubefix ollama
   ```
3. Install and configure [Ollama](https://ollama.com/) to run locally.

## Usage

To run the script, execute the following command in your terminal:

```bash
python script_name.py <YouTube_URL>
```

Example:

```bash
python script_name.py https://www.youtube.com/watch?v=dQw4w9WgXcQ
```

## How It Works

1. The script fetches the title and transcript of the specified YouTube video.
2. The transcript is passed to an AI model (like `deepseek-r1`) running locally via Ollama.
3. The AI summarizes the transcript into a structured and formatted post.
4. The generated post is saved as a Markdown file using the video title as the filename.

## Example Output

If the video title is `My Sample Video`, the script creates a file called `My Sample Video.md` containing the blog post.

## Local AI Model Usage

This script is designed to work with local AI models using Ollama. Ensure you have a model like `deepseek-r1` available locally by downloading it via Ollama:

```bash
ollama pull deepseek-r1:7B
```

### Ollama Model Configuration

The model is specified in the `summarize_text()` function:

```python
response: ChatResponse = chat(
    model="deepseek-r1:7B",
    messages=[
        {"role": "user", "content": prompt},
    ]
)
```

You can adjust the model based on your preferences.

## Error Handling

If any errors occur, the script logs the details and exits gracefully. Ensure you provide a valid YouTube URL and have internet access to fetch transcripts.

## Troubleshooting

- **No transcript available:** Some videos may not have transcripts enabled.
- **Model issues:** Ensure the specified AI model is correctly installed and available in Ollama.
- **File not saving:** Check if the title contains invalid filename characters.

## Contributing

Feel free to submit issues or pull requests to enhance this project.

## License

This project is licensed under the MIT License.
