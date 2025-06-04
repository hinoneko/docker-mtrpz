FROM node:20-slim AS builder

WORKDIR /app

COPY package*.json ./

RUN npm install --omit=dev

COPY . .

FROM gcr.io/distroless/nodejs20

WORKDIR /app

COPY --from=builder /app .

EXPOSE 3000

CMD ["index.js"]
