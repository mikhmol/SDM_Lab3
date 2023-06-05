# Use an official Python runtime as a parent image
FROM python:3

# Set the working directory in the container to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY ./spaceship /app/spaceship

# Update pip
RUN pip install --upgrade pip

# Install any needed packages specified in requirements.txt
RUN pip install fastapi pydantic starlette "uvicorn[standard]"

# Make port 8080 available to the world outside this container
EXPOSE 8080

# Define environment variable
ENV NAME World

# Run app.py when the container launches
CMD ["uvicorn", "spaceship.main:app", "--host=0.0.0.0", "--port=8080"]