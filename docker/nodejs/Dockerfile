# Stage 1 — builder
FROM node:20-alpine AS builder

WORKDIR /app

# Копируем только package.json и lock-файл для кэширования зависимостей
COPY package*.json ./

RUN npm ci --only=production

# Копируем исходный код
COPY . .

# Stage 2 — runtime
FROM node:20-alpine

WORKDIR /app

# Создаем пользователя без root
RUN addgroup -S appgroup && adduser -S appuser -G appgroup

COPY --from=builder /app /app

USER appuser

EXPOSE 3000

CMD ["node", "app.js"]
