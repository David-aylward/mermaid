# Mermaid Graph Editor


This simple app allows you to edit and render [Mermaid](https://mermaid-js.github.io/) diagrams directly in the browser. You can download the rendered graph as an SVG image and store frequently used snippets as templates using your browser's local storage. The interface is now styled with a vibrant gradient theme for a playful, modern feel. Rendering uses `mermaid.render` for better reliability when re-rendering after fixing errors.


## Usage

1. Open `index.html` in a browser.
2. Enter your Mermaid code in the text area and press **Render** to view the diagram.
3. Select **Download Image** to save the rendered diagram as `graph.svg`.
4. Click **Save Template** to store the current Mermaid code under a name of your choice. Use **Load Template** to select a saved template.

If your diagram contains syntax errors, an error message will appear below the controls.

Templates are stored locally in your browser using `localStorage` and are not synced anywhere else.

## Running a Local Server

You can serve the page locally with Python:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000` in your browser.

## AI Generation with Ollama

To create diagrams from natural language prompts, install [Ollama](https://github.com/jmorganca/ollama) and start its API server:

```bash
ollama serve
```

With the server running, use the **AI Generate** button in the editor. The text field labeled **Ollama API URL** lets you specify the API endpoint (default `http://localhost:11434`).
The list of models is fetched automatically from the server and shown in a drop-down so you can pick which one to use for generation.
Enter a prompt describing your diagram and the selected model will return Mermaid code that is placed in the editor automatically.
