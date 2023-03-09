# Enviando (push) arquivos para o Github

## O processo de envio segue alguns passos:

### Antes de enviar seus arquivos, baixe as alterações mais recentes do repositório para sua máquina:

`git pull`

### Em seguida, selecione os arquivos alterados para serem enviados:

`git add *`


### Quando todos os arquivos estão prontos para ser enviados, empacote-os através do commit:

`git commit -m "Descrição das modificações"`

Você também pode querer assinar seus commits. Commits assinados são sinalizados por _Verified_ no GitHub:

`git commit -m "Descrição das modificações" --gpg-sign=0041MARTON0SOBRESCREVEU0CODIGO6B6F26074B`

Para obter a chave GPM para assinar o commit, execute:

`gpg --list-secret-keys --keyid-format=long`

### Depois de feito o commit vamos enviá-los para a nuvem (GitHub):

`git push origin main`




* Atenção: se a pasta do projeto estiver dentro de um volume virtual Dokan/Dokany o seguinte erro retornará:

`fatal: could not lookup commit`

Faça o clone do repositório em outro volume de disco.


##### Criado por [Marton Lyra](https://github.com/MartonLyra) em 09/mar/2023.