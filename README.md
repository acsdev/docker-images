# Just run and be happy

cat ./splited-rpm/splited.tar.gz* > ./oracle-database-xe-18c-1.0-1.x86_64.tar.gz

tar -xvf ./oracle-database-xe-18c-1.0-1.x86_64.tar.gz

rm oracle-database-xe-18c-1.0-1.x86_64.tar.gz 

docker build -t oracle18.4.0-xe:latest -f Dockerfile.xe .
