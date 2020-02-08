# Just run and be happy

cat ./splited-rpm/splited.tar.gz* > ./oracle-database-xe-18.4.x86_64.tar.gz

tar -xvf ./oracle-database-xe-18.4.x86_64.tar.gz

rm oracle-database-xe-18.4.x86_64.tar.gz 

docker build -t oracle-18-4-0-xe:latest -f Dockerfile.xe .

## To Run after build image
mkdir -p ${HOST_DIR}

chmod -R 777 ${HOST_DIR}

docker run --name oracle-18c-xe \
  -p 8080:8080 \
  -p 1521:1521 \
  -p 5500:5500 \
  -e ORACLE_BASE=/opt/oracle \
  -e ORACLE_SID=XE \
  -e ORACLE_PDB=oracle \
  -e ORACLE_PWD=oracle \
  -v ${HOST_DIR}:/opt/oracle/oradata \
  --detach \
  --privileged \
  oracle-18-doc4-0-xe
