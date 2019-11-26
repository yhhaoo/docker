FROM node:latest

ENV APP_ROOT=/app
ENV APP_PORT=3000
ENV DB_HOST=nwdb1
ENV DB_PORT=3306
ENV DB_USER=root
ENV DB_PASSWORD=changeit

WORKDiR ${APP_ROOT}
ADD main.js .
ADD package.json .
ADD public public
ADD config config
ADD views views

RUN npm install


HEALTHCHECK --interval=60s --timeout=5s --retries=3 \
	CMD curl -f http://localhost:${APP_PORT} > /dev/null || exit 1
EXPOSE ${APP_PORT}

ENTRYPOINT ["node", "main.js"]
CMD [""}
