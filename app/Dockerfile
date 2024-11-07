# Utilisez l'image officielle de Node.js comme base
FROM node:14


# Copiez le fichier package.json et package-lock.json
COPY package*.json ./

# Installez les dépendances de l'application
RUN npm install

# Copiez le reste du code de l'application
COPY app.js .

COPY public .

COPY routes/route.js .

COPY views/home.ejs .



# Exposez le port 3000
EXPOSE 3000

# Commande pour démarrer l'application
CMD ["npm", "start"]

