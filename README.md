# coding-project-template

This is an application built using:

- Django
- React Native
- Docker
- Node.js

## Features

- Create reviews
- View reviews + dealerships
- Create account / sign in
- Run from container
- Backend using MongoDB, IBM Code Engine

## Get started

1. Clone repository
2. Set up Django server

```
cd fullstack-developer-capstone/server
pip install virtualenv
virtualenv venv
source venv/bin/activate
python3 -m pip install -U -r requirements.txt
python3 manage.py makemigrations
python3 manage.py migrate
python3 manage.py runserver
```

3. Build frontend

```
cd fullstack-developer-capstone/server/frontend
npm install
npm run build
```

4. Build database

```
cd fullstack-developer-capstone/server/database
docker build . -t nodeapp
docker-compose up
```

5. Deploy backend APIs (using IBM Code Engine)

```
cd fullstack-developer-capstone/server/djangoapp/microservices
docker build . -t us.icr.io/${SN_ICR_NAMESPACE}/senti_analyzer
docker push us.icr.io/${SN_ICR_NAMESPACE}/senti_analyzer
ibmcloud ce application create --name sentianalyzer --image us.icr.io/${SN_ICR_NAMESPACE}/senti_analyzer --registry-secret icr-secret --port 5000
```

6. Update .env

## 📹 Screenshots

### Homepage

![Homepage](/screenshots/screenshot1.png)

### Dealers

![Dealers](/screenshots/screenshot2.png)

### Add Review

![Add Review](/screenshots/screenshot3.png)

### Reviews

![Reviews](/screenshots/screenshot4.png)
