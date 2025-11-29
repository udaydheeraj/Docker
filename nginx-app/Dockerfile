FROM nginx:latest

# removing default nginx website
RUN rm -rf /usr/share/nginx/html/*


COPY index.html /usr/share/nginx/html/


# expose port 80

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
