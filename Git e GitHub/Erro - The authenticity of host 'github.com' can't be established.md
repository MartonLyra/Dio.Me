## Erro se comunicação com GitHub:

**The authenticity of host 'github.com (ip)' can't be established**

Para solucionar, adicione o domínio GitHub nos hosts confiáveis através do seguinte comando:

Git Bash:

`ssh-keyscan github.com >> ~/.ssh/known_hosts`

Observe que foi criado o arquivo texto known_hosts na pasta:

`C:\Users\[nome_usuario]\.ssh`


##### Criado por [Marton Lyra](https://github.com/MartonLyra) em 09/mar/2023.