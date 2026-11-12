FROM python:3.9-slim

# Set the working directory inside the container
WORKDIR /app

# Copy all files from the current directory to the container's working directory
COPY . .

# Install dependencies from the requirements file
RUN pip install --no-cache-dir --upgrade -r requirements.txt

# Hugging Face Spaces requires port 7860
EXPOSE 7860

# Define the command to start the application using Gunicorn
# - `-b 0.0.0.0:7860`: Binds the server to port 7860
# `app:rental_price_predictor_api` refers to the variable name in app.py
CMD ["gunicorn", "-w", "4", "-b", "0.0.0.0:7860", "app:rental_price_predictor_api"]
