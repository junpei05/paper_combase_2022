FROM python:3.8.12-slim

# Install system dependencies
RUN apt-get update -o Acquire::AllowInsecureRepositories=true && \
    apt-get install -y --no-install-recommends --allow-unauthenticated \
    build-essential \
    python3-dev \
    git \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Set working directory
WORKDIR /workspace

# Copy and install requirements
COPY requirements.txt /workspace/requirements.txt
RUN pip install --no-cache-dir -r /workspace/requirements.txt

# Register Jupyter kernel (optional: shows up in VSCode kernel list)
RUN python -m ipykernel install --user --name combase_2022 --display-name "Python (ComBase_2022)"
