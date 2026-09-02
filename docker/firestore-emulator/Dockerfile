FROM node:20-alpine

RUN apk add --no-cache openjdk17-jre bash

RUN npm install -g firebase-tools@13.29.1

# Pre-download the emulator binaries so containers start without network access.
RUN firebase setup:emulators:firestore && firebase setup:emulators:ui

WORKDIR /firestore

COPY start.sh .
COPY firebase.json .
COPY .firebaserc .

ENTRYPOINT ["./start.sh"]
