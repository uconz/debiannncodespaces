FROM debian:trixie

# Definir variáveis para o usuário e senha
ENV USERNAME=leonel
ENV PASSWORD=1234
ENV LANG=pt_BR.UTF-8
ENV LANGUAGE=pt_BR:pt
ENV LC_ALL=pt_BR.UTF-8

# Atualizar pacotes, instalar sudo e configurar o idioma
RUN apt update && apt install -y sudo locales && \
    echo "pt_BR.UTF-8 UTF-8" > /etc/locale.gen && \
    locale-gen && \
    update-locale LANG=pt_BR.UTF-8

# Criar usuário e definir senha
RUN useradd -m -s /bin/bash $USERNAME && \
    echo "$USERNAME:$PASSWORD" | chpasswd && \
    usermod -aG sudo $USERNAME

# Definir usuário padrão ao iniciar o container
USER leonel
WORKDIR /home/leonel

CMD ["/bin/bash"]
