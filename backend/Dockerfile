# Use an official Python image as the base image
FROM python:3.9

# Set the working directory inside the container
WORKDIR /app

# Install Poetry
RUN curl -sSL https://install.python-poetry.org | python3 -

# Add Poetry to PATH
ENV PATH="/root/.local/bin:$PATH"

# Copy pyproject.toml and poetry.lock for Poetry dependencies
COPY pyproject.toml poetry.lock* ./

# Install dependencies using Poetry
RUN poetry install --no-root --no-dev

# Copy the rest of the application code
COPY . .

# Expose port 8000
EXPOSE 8000

# Run the prestart script to set up the database
RUN poetry run bash ./prestart.sh

# Command to run the application
CMD ["poetry", "run", "uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]
