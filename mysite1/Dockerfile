From python:3.11

ENV PYTHONBUFFERED 1

WORKDIR / app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

RUN python manage.py collectstatic --noinput

#CMD ["gunicorn", "mysite1.wsgi:application", "--bind", "0.0.0.0:8000"]
CMD ["sh", "-c", "python manage.py collectstatic --noinput && gunicorn mysite1.wsgi:application --bind 0.0.0.0:8000"]
