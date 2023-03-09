# SSH e GPG KEYS

Tanto as SSH quanto as GPG são chaves de criptografias. 
**As chaves SSH** são usadas para se comunicar com o GitHub e permitir acessar os repositórios (push, pull).
Já **as chaves GPG** são usadas para assinar os commits. 


## SSH Keys:



- Após gerar as chaves SSH públicas, no seu computador é necessário importá-la para o Hithub. Com essas chaves SSH, é possível se conectar ao Gitub sem fornecer seu nome de usuário e senha a cada visita. A chave também pode ser usada para assinar confirmações.


#### Para obter uma lista das chaves SSH existentes no seu computador:

- Navegue para pasta `C:\Users\\_nomeUsuarioWindows_\\.ssh`
ou digite no Git Bash:
`$ ls -al ~/.ssh`


#### Para gerar uma Chave SSH no seu computador:

No terminal Git Bash, digite:

`ssh-keygen -t ed25519 -C "seu_email@sua_empresa.com.br"`

- **No seu computador**, com seu editor de texto, abra o arquivo gerado (por padrão, em `C:\Users\nomeUsuarioWindows\.ssh`) com a extensão `.pub` (que faz referência a chave pública) e copie todo o conteúdo;
- **No site do GitHub** > Profile > Settings > SSH and GPG Keys > SSH Keys, crie nova chave e cole o conteúdo do arquivo.


#### Adicionando uma chave SSH ao ssh-agent:

- Para adicionar a chave SSH ao agente, é necessário inicializar o ssh-agent. Para isso execute no Git Bash:
`eval "$(ssh-agent -s)"`

A resposta será algo parecido com:
Agent pid 59566

E, para adicionar a chave, digite (substitua id_ed25519 pelo nome do arquivo):

`$ ssh-add ~/.ssh/id_ed25519`

A resposta será algo parecido com:

`Identity added: /c/Users/MartonJr/.ssh/id_ed25519 (marton2050@gmail.com)`



## GPG Keys:

- Para assinar commits localmente, você precisa informar ao Git qual a chave GPG você deseja usar.

- Observe que, ao gerar a chave GPG Key, você informa o seu eMail. 

- Certifique-se de ter o [GPG Cli](https://www.gnupg.org/download/) instalado no computador.

#### Para obter uma lista das chaves GPG existentes no seu computador:

Digite no Git Bash:
`gpg --list-secret-keys --keyid-format=long`


### Para gerar o par de chaves GPG:

https://docs.github.com/en/authentication/managing-commit-signature-verification/generating-a-new-gpg-key






#### [Para gerar uma Chave GPG no seu computador:](https://docs.github.com/en/authentication/managing-commit-signature-verification/generating-a-new-gpg-key)

- Digite no Git Bash:
`gpg --full-generate-key`

- Escolha qual tipo de chave você deseja - opção padrão: `(1) RSA and RSA`.

- A pergunta seguinte é sobre o tamanho da chave. Escolha, pelo menos 4096 bits para usar no GitHub.

- Responda sobre a validade da chave onde, por padrão, não expira nunca.

- Em seguida responda seu nome e **seu endereço de eMail**. Importante: seu endereço de eMail deve estar cadastrado no GitHub na seção ['Setting > eMails'](https://github.com/settings/emails). MartonJr usou seu eMail particular marton2050@gmail.com

- Os arquivos criados podem ser localizados na pasta `C:\Users\[nome_usuário]\.gnupg`

- O id da chave gerada é uma sequencia de 16 caracteres, por exemplo: `2DB76517343C5AA3`

- Para obter a chave no formato ASCII, execute o seguinte comando, substituindo o último parâmetro pelo id da chave criada:
`gpg --armor --export 2DB76517343C5AA3`

- Copie o resultado (começando com "-----BEGIN PGP PUBLIC KEY BLOCK-----" e terminando com "-----END PGP PUBLIC KEY BLOCK-----") e [adicione a chave GPG na sua conta do GitHub](https://github.com/settings/keys) em Perfil > Settings > SSH and GPG Keys > New GPG Key.

- Na lista GPG Keys, do GitHub, a chave aparecerá mostrando o eMail da chave e sua Key Id, podendo ser conferido sempre que precisar.

#### Detalhes:

- Se você não tiver usado sua chave SSH por um ano, o GitHub excluirá automaticamente essa chave SSH inativa como uma medida de segurança.
- A partir da versão de 2022, é possível usar as chaves SSH para assinar os commits. Porém, essa prática não é recomendável.




Mais informações:
https://docs.github.com/pt/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent



##### Criado por [Marton Lyra](https://github.com/MartonLyra) em 08/mar/2023.