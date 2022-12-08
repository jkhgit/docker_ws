Dockerfile
==================
ubuntu:20.04
::
  FROM ubuntu:20.04
  ARG DEBIAN_FRONTEND=noninteractive

  # shell: bash
  SHELL ["/bin/bash", "-c"]

  # vars
  ENV ID="steve" \
      TZ="Asia/Seoul"

  # timezone set 
  RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

  # preinstall & set user account
  WORKDIR /root
  COPY docker.preinst preinst
  COPY docker.user user
  RUN chmod +x preinst user && \
      ./preinst && ./user $ID
  RUN rm preinst user

  # change root to user
  USER $ID

  # build sequence as user
  WORKDIR /home/$ID

  ...
