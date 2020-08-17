admin:
	docker run -d --name wlsadmin --hostname wlsadmin -p 7001:7001 \
      -v /c/Users/jason/dev/oracle-docker-images/OracleWeblogic/samples/12213-domain-home-in-image/properties/docker-run:/u01/oracle/properties \
      12213-domain-home-in-image

managed:
	docker run -d --name MS1 --link wlsadmin:wlsadmin -p 8001:8001 \
      -v /c/Users/jason/dev/oracle-docker-images/OracleWeblogic/samples/12213-domain-home-in-image/properties/docker-run:/u01/oracle/properties \
      -e MANAGED_SERV_NAME=managed-server1 12213-domain-home-in-image startManagedServer.sh

build-jre:
	cd OracleJava/8 && docker build -t oracle/serverjre:8 .