FROM python
ENV FLASK_APP app.py
COPY . .
RUN apt-get update && pip install -r requirements.txt
CMD ["flask", "run", "--host=0.0.0.0", "--port=80"]
EXPOSE 80