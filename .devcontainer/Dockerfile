FROM debian:latest

ENV USERNAME=leonel
ENV PASSWORD=1234

RUN apt update && apt install -y sudo

RUN useradd -m -s /bin/bash $USERNAME && \
    echo "$USERNAME:$PASSWORD" | chpasswd && \
    usermod -aG sudo $USERNAME

USER leonel
WORKDIR /home/leonel

CMD ["/bin/bash"]
