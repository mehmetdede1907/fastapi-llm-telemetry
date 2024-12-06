# FastAPI LLM Telemetry Demo

This project demonstrates how to implement OpenTelemetry instrumentation for monitoring LLM API calls and error tracking in a FastAPI application.

## Features

- FastAPI REST API with LLM completion endpoint
- OpenTelemetry integration for distributed tracing
- Automatic instrumentation of FastAPI and HTTP requests
- Custom spans for LLM API calls with detailed metadata
- Error tracking and propagation
- Integration with Anthropic's Claude API

## Setup

1. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

2. Set up environment variables:
   ```bash
   ANTHROPIC_API_KEY=your_api_key
   OTLP_ENDPOINT=http://localhost:4317  # Your OpenTelemetry collector endpoint
   ENVIRONMENT=development
   ```

3. Run the application:
   ```bash
   uvicorn main:app --reload
   ```

## API Endpoints

- POST `/completion`: Get LLM completion
  ```json
  {
    "prompt": "Your prompt here",
    "max_tokens": 1000
  }
  ```

- GET `/health`: Health check endpoint

## OpenTelemetry Integration

The application uses OpenTelemetry to track:
- HTTP requests and responses
- LLM API calls with prompt and response metadata
- Error propagation and tracking
- Custom business metrics

## Monitoring

The application exports traces to an OpenTelemetry collector. You can visualize these traces using tools like:
- Jaeger
- Zipkin
- DataDog
- New Relic

## Development

1. Install development dependencies:
   ```bash
   pip install -r requirements.txt
   ```

2. Run tests:
   ```bash
   pytest
   ```

## License

MIT