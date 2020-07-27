# HOST image - used to create containers to be managed by master

# use builded ansible_base (defined in ../base/Dockerfile) as a starting point
FROM ansible_base:latest
#added this by me
RUN apt-get update && apt-get install -y dos2unix
# copy script from local disk to file system inside Docker image
COPY run.sh /var/

# adjust file permissions to make run.sh executable
RUN chmod 755 /var/run.sh
#added by me
RUN dos2unix /var/run.sh && apt-get --purge remove -y dos2unix && rm -rf /var/lib/apt/lists/*
ENTRYPOINT ["var/run.sh"]
