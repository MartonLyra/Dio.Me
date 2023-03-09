# Clone de Repositório - Configurando máquina local para uso

- Navegue até o reposistório desejado, no GitHub, e clique no botão **Code**

Você verá três formas de clonar o repositório:

### HTTPS:

Use Git com a URL HTTPS do repositório:

git clone *url_https_do_repositório*

### SSH:

Use uma chave SSH protegida por password:

git clone *url_ssh_do_repositório*

*Essa é a melhor opção para evitar autenticar-se com frequência.


### GitHub CLI:

Execute o comando especificado na ferramenta CLI. Exemplo:

gh repo clone MartonLyra/Dio.Me


### Detalhes:

- se a pasta do projeto estiver dentro de um volume virtual Dokan/Dokany, futuramente dará erro no comando git commit. Faça o clone do repositório em outro volume de disco.


##### Criado por [Marton Lyra](https://github.com/MartonLyra) em 09/mar/2023.