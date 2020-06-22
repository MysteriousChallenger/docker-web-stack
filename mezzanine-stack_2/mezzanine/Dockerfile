FROM python:3
WORKDIR /usr/src/app

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt
RUN mezzanine-project mezzanine_site
RUN python ./mezzanine_site/manage.py createdb --noinput || :
EXPOSE 80/tcp
ENTRYPOINT ["python", "./mezzanine_site/manage.py", "runserver", "0.0.0.0:80"]