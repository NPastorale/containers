FROM node:22.14.0-alpine AS builder

WORKDIR /app

RUN mkdir /app/dist
RUN mkdir /app/dist/css

RUN npm install html-minifier postcss-cli cssnano

COPY . .

RUN npx html-minifier --input-dir . --output-dir ./dist --file-ext html --collapse-whitespace --remove-comments --minify-js true --minify-css true

RUN rm -rf /app/dist/node_modules

RUN npx postcss-cli ./css/*.css --use cssnano --dir ./dist/css --no-map

RUN cp -r ./images ./dist/images

RUN ls -la /app/dist

FROM nginx:1.27.5-alpine-slim@sha256:b947b2630c97622793113555e13332eec85bdc7a0ac6ab697159af78942bb856

RUN rm -rf /usr/share/nginx/html/*

COPY --from=builder /app/dist /usr/share/nginx/html/