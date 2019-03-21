FROM openjdk:8-jre-alpine AS final
RUN apk add bash
# this is expected to be mounted from the host and should
# have cromwell.jar and cromwell.conf
WORKDIR /opt/scripts
RUN printf "#!/bin/bash\njava -Dconfig.file=cromwell.conf -jar cromwell.jar \"\$@\"" > cromwell.sh
RUN chmod +x cromwell.sh

WORKDIR /opt/cromwell
EXPOSE 8000
ENTRYPOINT ["/opt/scripts/cromwell.sh"]
CMD ["server"]
