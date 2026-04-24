## Installation

### 1. Install `uv`

Choose one method:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

or

```bash
brew install uv
```

### 2. Install dependencies

```bash
uv sync
```

### 3. Configure environment variables

Create a `.env` file in the project root.

```env
OPENAI_API_KEY=your_api_key
```

## Usage

### 3. Run the demo

```bash
uv run chainlit run demo.py
```

The chatbot will be available at `http://localhost:8000`.

### Example Queries

- "Get AAPL stock information"
- "Show me recent TSLA news"
- "Display NVDA price history for the past month"
- "Show me a candlestick chart for MSFT over the last 3 months"
