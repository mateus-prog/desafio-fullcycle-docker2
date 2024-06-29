FROM node:14 AS builder

WORKDIR /app

COPY . .

RUN apt update && \
    apt install -y wget netcat-traditional && \
    wget -q -O /usr/bin/wait-for https://raw.githubusercontent.com/eficode/wait-for/v2.2.3/wait-for && \
    chmod +x /usr/bin/wait-for

RUN npm i

EXPOSE 3000

CMD ["wait-for", "db:3306", "--", "npm", "start"]