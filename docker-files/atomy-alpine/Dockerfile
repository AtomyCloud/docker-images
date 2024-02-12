# Atomy Alpine Container Image | atomy-alpine:1.0
FROM atomycloud/base:alpine-v3.19.1

# Update apk repositories
RUN apk update

# Install tools
RUN apk add sudo bash nano htop ipcalc

# Run a bash shell when the container launches
CMD [ "/bin/bash" ]