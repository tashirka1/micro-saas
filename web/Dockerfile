FROM node:lts-slim AS build
WORKDIR /app
COPY package.json package-lock.json .
COPY . .
RUN npm install
RUN npm run build

FROM node:lts-slim AS run
WORKDIR /app
COPY --from=build /app/build ./build
EXPOSE 3000
CMD ["node", "build"]
