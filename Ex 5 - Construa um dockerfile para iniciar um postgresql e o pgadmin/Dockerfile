FROM postgres:latest
ENV POSTGRES_USER=postgres
ENV POSTGRES_PASSWORD=1234
ENV POSTGRES_DB=postgres
EXPOSE 5432

FROM dpage/pgadmin4:latest
ENV PGADMIN_DEFAULT_EMAIL=admin@pgadmin.org
ENV PGADMIN_DEFAULT_PASSWORD=admin
EXPOSE 80

CMD ["./usr/local/bin/start.sh"]
