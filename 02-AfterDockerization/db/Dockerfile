FROM mysql:5.7.22
EXPOSE 3306
COPY ./DockerFromZeroToMastery/db/migrations/ /home/database/
COPY ./DockerFromZeroToMastery/db/dataset/ /home/database/
COPY ./DockerFromZeroToMastery/ci/init_database.sh /docker-entrypoint-initdb.d/init_database.sh