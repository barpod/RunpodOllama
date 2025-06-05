# Use an official base image with your desired version
FROM ollama/ollama:0.9.0

ENV PYTHONUNBUFFERED=1 

# Set up the working directory
WORKDIR /

RUN apt-get install --reinstall ca-certificates

RUN apt-get update && apt-get install -y \
    python3 \
    python3-pip \
    python3-dev \
    build-essential \
    curl \
    && rm -rf /var/lib/apt/lists/*

# Add your file
ADD . .

RUN pip install runpod

# Override Ollama's entrypoint
ENTRYPOINT ["bin/bash", "start.sh"]

CMD ["qwen3:30b-a3b"]

