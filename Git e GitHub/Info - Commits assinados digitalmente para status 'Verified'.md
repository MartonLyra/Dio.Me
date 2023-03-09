# Caso seus commits não estejam com status 'Verified', no GitHub, verifique:

- Digite o comando abaixo e verifique seu nome e eMail.

git config --global --edit

- Gere uma chave GPG usando o seu eMail.

- Após gerar a chave GPG, consulte a lista de chaves com o Git Bash:

`gpg --list-secret-keys --keyid-format=long`

```sh
gpg: checking the trustdb
gpg: marginals needed: 3  completes needed: 1  trust model: pgp
gpg: depth: 0  valid:   1  signed:   0  trust: 0-, 0q, 0n, 0m, 0f, 1u
/c/Users/MartonJr/.gnupg/pubring.kbx
------------------------------------
sec   rsa4096/66C64B6B6F26074B 2023-03-09 [SC]
      0041MARTON0SOBRESCREVEU0CODIGO6B6F26074B
uid                 [ultimate] Marton Lyra (Marton Lyra) <marton2050@gmail.com>
ssb   rsa4096/8F0DB78796840130 2023-03-09 [E]
```


- Ao realizar o commit, use a flag `--gpg-sign=CodigoSec40Chars`
Exemplo:
`git commit -m "Descrição das modificações" --gpg-sign=0041MARTON0SOBRESCREVEU0CODIGO6B6F26074B`



##### Criado por [Marton Lyra](https://github.com/MartonLyra) em 09/mar/2023.