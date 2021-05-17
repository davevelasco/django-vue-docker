# Pull python image
FROM python:3.9.5-alpine

# Set working directory
WORKDIR /app

# Set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Install psycopg2 dependencies
RUN apk update && apk add postgresql-dev gcc python3-dev musl-dev

# Install dependencies
RUN pip install --upgrade pip
COPY requirements.txt ./
RUN pip install -r requirements.txt

# Copy entrypoint
COPY entrypoint.sh .

# Copy project
COPY . .

ENTRYPOINT ["/app/entrypoint.sh"]

# Run python development server
EXPOSE 8000
CMD ["python", "manage.py", "runserver", "0:8000"]
