FROM node:lts-alpine AS build
WORKDIR /app
COPY package.json package-lock.json ./
COPY . .
RUN npm install
RUN npm run build

FROM node:lts-alpine AS run
WORKDIR /app
COPY --from=build /app/build ./build
RUN adduser --disabled-password --gecos "" appuser && \
    chown -R appuser:appuser /app
USER appuser
EXPOSE 3000
CMD ["node", "build"]
