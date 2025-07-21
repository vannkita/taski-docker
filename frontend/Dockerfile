FROM node:18
WORKDIR /app

COPY package.json package.json
COPY package-lock.json package-lock.json

RUN npm install

COPY . .
RUN npm run build

CMD ["npx", "-y", "http-server", "/app/build", "-p", "3000", "-a", "0.0.0.0", "--proxy", "http://localhost:8000?"]
