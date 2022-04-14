# Imagem base mínima (5.59MB)
FROM alpine:3.14

# Instala o programa thttpd.
RUN apk add thttpd

# Cria um novo usuário simples que não tem permissões de root
RUN adduser -D static
USER static

# Cria-se um nova pasta dentro da imagem
WORKDIR /home/static

# Copia arquivo HTML para dentro da imagem
COPY index.html index.html

# Executa o programa thttpd para entregar arquivos HTML na pasta "/home/static"
CMD ["thttpd", "-D", "-h", "0.0.0.0", "-p", "3000", "-d", "/home/static", "-u", "static", "-l", "-"]
