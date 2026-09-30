# Deepseek Token Optimizer

A comprehensive toolkit to monitor, analyze, and reduce Deepseek API token usage. Track billions of tokens and optimize your spending.

## Features

- **Token Usage Monitoring** - Real-time tracking of API consumption
- **Cost Analysis** - Understand where your tokens are going
- **Prompt Optimization** - Reduce tokens per request
- **Caching Layer** - Avoid redundant API calls
- **Batch Processing** - Efficient request grouping
- **Rate Limiting** - Control spending with quotas
- **Usage Analytics** - Detailed breakdown and trends

## Quick Start

### 1. Install Dependencies
```bash
pip install -r requirements.txt
```

### 2. Set Up Configuration
```bash
cp config.example.yaml config.yaml
```

Edit `config.yaml` with your Deepseek API key:
```yaml
deepseek:
  api_key: "your-api-key-here"
  base_url: "https://api.deepseek.com/v1"
  
optimization:
  enable_caching: true
  enable_batching: true
  max_tokens_per_minute: 100000
  
monitoring:
  log_level: "INFO"
  alert_threshold: 1000000  # Alert when daily usage exceeds this
```

### 3. Run the Monitor
```bash
python monitor.py
```

## Core Components

### `monitor.py`
Real-time token usage monitoring and alerting

```bash
python monitor.py --interval 60 --alert-email your@email.com
```

### `optimizer.py`
Analyze and optimize your prompts to use fewer tokens

```bash
python optimizer.py --analyze-file requests.log
```

### `cache.py`
Intelligent caching to prevent duplicate API calls

```bash
from cache import TokenCache
cache = TokenCache(ttl=3600)
response = cache.get_or_fetch(prompt, model)
```

### `cost_analyzer.py`
Detailed breakdown of token usage and costs

```bash
python cost_analyzer.py --date 2026-09-30 --output report.csv
```

## Token Reduction Strategies

### 1. **Prompt Optimization**
- Remove unnecessary context
- Use concise language
- Avoid redundant instructions
- Structure prompts efficiently

### 2. **Caching**
- Cache repeated queries
- Store common responses
- Implement TTL strategies

### 3. **Batching**
- Group similar requests
- Reduce round-trips
- Process in bulk

### 4. **Context Management**
- Limit conversation history
- Archive old sessions
- Summarize long contexts

### 5. **Model Selection**
- Use appropriate model sizes
- Reserve heavy models for complex tasks
- Use lighter models for simple queries

## Usage Examples

### Monitor Daily Usage
```bash
python monitor.py --daily-report
```

### Get Cost Breakdown
```bash
python cost_analyzer.py --format json > usage.json
```

### Optimize a Prompt File
```bash
python optimizer.py --analyze-file my_prompts.txt --suggest-improvements
```

### Set Token Budget
```bash
python budget.py --set-daily-limit 500000000
```

## API Reference

See `docs/API.md` for detailed API documentation.

## Contributing

Contributions are welcome! Please submit issues and pull requests.

## License

MIT License - See LICENSE file for details
