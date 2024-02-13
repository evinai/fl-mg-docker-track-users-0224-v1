FROM python:3
WORKDIR /usr/src/app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
# . first dot is for the files in crnt working directory . second dot is the workdir
COPY . . 
CMD ["python", "app.py"]