FROM nginx

COPY nginx.conf /etc/nginx

RUN mkdir /index
COPY index.html /index
CMD nginx -c /etc/nginx/nginx.conf