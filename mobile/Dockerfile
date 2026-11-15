# Development only: runs the Metro bundler for Expo Go / dev builds on the LAN.
# Release apps are built with EAS (eas.json), not from this image.
FROM node:26.13.0-alpine@sha256:8996bb5821d62a8fd9bb27c1cb07462f3fdce6e47d640c6a881ead0b064ce216

WORKDIR /app

# Dependencies first (cached layer), exactly as locked
COPY package.json package-lock.json ./
RUN npm ci

COPY . .

# Metro
EXPOSE 8081

CMD ["npx", "expo", "start", "--lan"]
