FROM v8tix/cronov:0.0.4.v20200324.0efd158
LABEL MAINTAINER="V8TIX"
LABEL MAIL="info@v8tix.com"
RUN ["/bin/bash", "-c", "mkdir /usr/lib/jvm"]
ADD \
  https://corretto.aws/downloads/resources/11.0.6.10.1/amazon-corretto-11.0.6.10.1-linux-x64.tar.gz \
  /usr/lib/jvm/
ADD entrypoint /home/v8tix/entrypoint
RUN ["/bin/bash", "-c", "/home/v8tix/libraries/zemni/execution/java/java.sh"]
RUN ["/bin/bash", "-c", "/home/v8tix/libraries/zemni/system/sec/remove_all_perm.sh"]
ENTRYPOINT ["/home/v8tix/entrypoint/entrypoint.sh"]
# Do not set the default user in the base otherwise
# implementations will not be able to update the image
# USER v8tix:v8tix