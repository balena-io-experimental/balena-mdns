FROM balenalib/amd64-debian-node:12.22-bullseye-build as builder

WORKDIR /usr/src/app

COPY . ./
RUN JOBS=MAX npm install --production --unsafe-perm && npm --force cache clean && rm -rf /tmp/*

FROM balenalib/amd64-debian-node:12.22-bullseye-run

RUN install_packages bash
COPY --from=builder /usr/src/app/node_modules node_modules
COPY mdns-resolve.js /bin

ENTRYPOINT ["node", "/bin/mdns-resolve.js"]
