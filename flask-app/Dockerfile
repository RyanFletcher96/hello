# Use Slim for better compatibility with Python packages
FROM python:3.11-slim

WORKDIR /flask-app

# Copy our NEW minimal requirements file
COPY requirements.docker.txt ./requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the app code
COPY . .

EXPOSE 8080

# Bind to 0.0.0.0 so the container can talk to your laptop
CMD ["gunicorn", "--workers", "3", "--bind", "0.0.0.0:8080", "app:app"]