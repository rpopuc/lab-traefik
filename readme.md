# Traefik

Este é um estudo de configuração do Traefik como proxy reverso baseado nas instruções desse [vídeo](https://www.youtube.com/watch?v=wLrmmh1eI94).

O exemplo exposto nesse laboratório baseia-se no arquivo `config/traefik/trafik.yml`. Os pontos principais de configuração desse arquivo são dois `entrypoints`: web, na porta 80 e websecure, na porta 443. Também é configurado que todo acesso à porta 80 deve ser redirecionado para a porta 443. Os certificados são gerados automaticamente, via LetsEncrypt. Para uso local, é utilizado um certificado auto-assinado.

A configuração dos hosts é feita dinamicamente, com uso das labels registradas nos containers do docker. Para que as configurações dos labels tenham efeito sobre o Traefik, todos têm de estar sob a mesma rede. Para as configurações disponíveis nas labels, vale consultar essa [documentação](https://doc.traefik.io/traefik/routing/routers/).

