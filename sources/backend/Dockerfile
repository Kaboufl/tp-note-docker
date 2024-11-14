FROM python:3.12

WORKDIR /usr/src/app

COPY ./requirements.txt ./

RUN pip install Flask waitress
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 8080

CMD ["waitress-serve", "--host", "0.0.0.0", "--call", "flaskr:create_app"]
