FROM python:3.10-slim

WORKDIR /app

# Copy requirements and wheel file
COPY requirements.txt .
COPY *.whl .

# Install dependencies
RUN pip install --no-cache-dir --upgrade pip
RUN pip install --no-cache-dir -r requirements.txt --ignore-installed
RUN pip install --no-cache-dir *.whl --ignore-installed

# Copy the rest of the application
COPY . .

# Expose port
EXPOSE 8000

# Command to run the application
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]