# Use an official Python runtime as a parent image
FROM python:3

# Set the working directory in the container to /app
WORKDIR /app

# Update pip
RUN pip install --upgrade pip

COPY ./requirements /app/requirements

# Install any needed packages specified in requirements.txt
RUN pip install -r requirements/backend.in

# Copy the current directory contents into the container at /app
COPY ./spaceship /app/spaceship

# Make port 8080 available to the world outside this container
EXPOSE 8080

# Define environment variable
ENV NAME World

# Run app.py when the container launches
CMD ["uvicorn", "spaceship.main:app", "--host=0.0.0.0", "--port=8080"]