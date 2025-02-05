# Use a minimal base image
FROM python:3.9-alpine

# Set environment variables
ENV PYTHONUNBUFFERED=1

# Create a non-root user
RUN addgroup -S appgroup && adduser -S appuser -G appgroup

# Set the working directory
WORKDIR /app

# Copy only necessary files
COPY app.py requirements.txt ./

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Switch to non-root user
USER appuser

# Expose the application port
EXPOSE 8080

# Run the application
CMD ["python", "app.py"]
