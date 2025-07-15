# OCR API

A simple Flask-based OCR (Optical Character Recognition) API that extracts text from images using Tesseract OCR engine.

## Features

- Extract text from uploaded images
- Health check endpoint for monitoring
- Docker containerization for easy deployment
- Built with Flask and Tesseract OCR

## Prerequisites

- Docker (includes Docker Compose)

## Quick Start with Docker

### Option 1: Using Docker Compose (Recommended)

1. Clone the repository:
```bash
git clone <your-repository-url>
cd ocr-api
```

2. Start the service:
```bash
docker compose up -d
```

The API will be available at `http://localhost:9000`

## API Endpoints

### 1. Health Check

**Endpoint:** `GET /health`

Checks if the API service is running properly.

**Request:**
- Method: `GET`

**Example using curl:**
```bash
curl http://localhost:9000/health
```

### 2. OCR Text Extraction

**Endpoint:** `POST /ocr`

Extracts text from an uploaded image.

**Request:**
- Method: `POST`
- Content-Type: `multipart/form-data`
- Body: Form data with an `image` field containing the image file

**Example using curl:**
```bash
curl -X POST http://localhost:9000/ocr \
  -F "image=@path/to/your/image.jpg"
```

## Project Structure

```
ocr-api/
├── app/
│   └── main.py          # Flask application
├── Dockerfile           # Docker configuration
├── docker-compose.yml   # Docker Compose configuration
├── requirements.txt     # Python dependencies
└── README.md          # This file
```