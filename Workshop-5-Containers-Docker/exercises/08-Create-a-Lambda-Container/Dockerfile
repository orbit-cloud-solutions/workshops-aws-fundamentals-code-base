FROM debian:11
ARG FUNCTION_DIR="/opt/lambda/"
RUN apt-get -y update && apt-get -y upgrade && apt-get -y install python3 python3-pip && apt-get -y clean
RUN mkdir -p ${FUNCTION_DIR}
WORKDIR ${FUNCTION_DIR}
RUN pip install awslambdaric
COPY app/* ${FUNCTION_DIR}
ENTRYPOINT ["/opt/lambda/start.sh"]
CMD ["index.handler"]
