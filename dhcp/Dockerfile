# Use a imagem base do Ubuntu
FROM ubuntu:latest

# Atualize os repositórios de pacotes e instale o servidor DHCP
RUN apt-get update && apt-get install -y isc-dhcp-server

# Crie o diretório para o banco de dados de arrendamento
RUN mkdir -p /var/lib/dhcp/

# Copie o arquivo de configuração do DHCP para dentro do contêiner
COPY dhcpd.conf /etc/dhcp/dhcpd.conf

# Exponha a porta usada pelo servidor DHCP
EXPOSE 67/udp

RUN mkdir -p /var/lib/dhcp/
# Comando para iniciar o servidor DHCP
CMD ["dhcpd", "-f", "-d", "--no-pid", "-cf", "/etc/dhcp/dhcpd.conf"]
