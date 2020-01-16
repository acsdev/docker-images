# Just run and be happy

cat ./splited-rpm/splited.tar.gz* > ./oracle-database-xe-18.4.x86_64.tar.gz

tar -xvf ./oracle-database-xe-18.4.x86_64.tar.gz

rm oracle-database-xe-18.4.x86_64.tar.gz 

docker build -t oracle-18-4-0-xe:latest -f Dockerfile.xe .
