# --------------- DÉBUT COUCHE OS -------------------
FROM python:2.7-stretch


# --------------- MÉTADONNÉES DE L'IMAGE ---------------
LABEL version="1.0" maintainer="DND Nicolas<dounmogni@yahoo.fr>"


# --------------- DÉBUT COUCHE APPLICATIVE ----------------
RUN DEBIAN_FRONTEND=noninteractive apt-get update -y && apt-get install python-dev python3-dev libsasl2-dev python-dev libldap2-dev libssl-dev -y

RUN pip install flask==1.1.2 flask_httpauth==4.1.0 flask_simpleldap python-dotenv==0.14.0
                   
                   # -- copy du script dans la racine du conteneur
COPY ./student_age.py /
# --------------- FIN COUCHE APPLICATIVE ----------------


# ---------------  OUVERTURE DU PORT HTTP ------------------
EXPOSE 5000

# ---------------  CREATION DU VOLUME PARTAGE ------------------
VOLUME /data/

# --------------- DÉMARRAGE DES SERVICES LORS DE L'EXÉCUTION DE L'IMAGE ------------------
CMD [ "python", "./student_age.py" ]