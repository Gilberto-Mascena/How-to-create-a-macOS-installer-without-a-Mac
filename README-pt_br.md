[Português Brasileiro](https://github.com/Gilberto-Mascena/How-to-create-a-macOS-installer-without-a-Mac/blob/main/README-pt_br.md) | 
[English](https://github.com/Gilberto-Mascena/How-to-create-a-macOS-installer-without-a-Mac/blob/main/README.md)

[![Status de Manutenção](https://img.shields.io/badge/Maintained-Yes-brightgreen?style=for-the-badge)](https://GitHub.com/Gilberto-Mascena/How-to-create-a-macOS-installer-without-a-Mac)
[![GitHub Actions Status](https://img.shields.io/github/actions/workflow/status/Gilberto-Mascena/How-to-create-a-macOS-installer-without-a-Mac/build.yml?style=for-the-badge)](https://github.com/Gilberto-Mascena/How-to-create-a-macOS-installer-without-a-Mac/actions)
[![Licença](https://img.shields.io/github/license/Gilberto-Mascena/How-to-create-a-macOS-installer-without-a-Mac?style=for-the-badge)](https://github.com/Gilberto-Mascena/How-to-create-a-macOS-installer-without-a-Mac/blob/main/LICENSE.md)
[![Estrelas no GitHub](https://img.shields.io/github/stars/Gilberto-Mascena/How-to-create-a-macOS-installer-without-a-Mac?style=for-the-badge)](https://github.com/Gilberto-Mascena/How-to-create-a-macOS-installer-without-a-Mac/stargazers)
[![Problemas no GitHub](https://img.shields.io/github/issues/Gilberto-Mascena/How-to-create-a-macOS-installer-without-a-Mac?style=for-the-badge)](https://github.com/Gilberto-Mascena/How-to-create-a-macOS-installer-without-a-Mac/issues)
[![Versão do Repositório](https://img.shields.io/github/v/release/Gilberto-Mascena/How-to-create-a-macOS-installer-without-a-Mac?include_prereleases&style=for-the-badge)](https://github.com/Gilberto-Mascena/How-to-create-a-macOS-installer-without-a-Mac/releases)
![Data de Lançamento](https://img.shields.io/github/release-date/Gilberto-Mascena/How-to-create-a-macOS-installer-without-a-Mac?style=for-the-badge)
![Tamanho do Repositório](https://img.shields.io/github/repo-size/Gilberto-Mascena/How-to-create-a-macOS-installer-without-a-Mac?style=for-the-badge)

# _Como criar um instalador do macOS genuíno sem acesso a um Mac?_

<div align="center">
    <img src="./assets/miscellany/macOS-recovery.png" width="150">
</div>

### _Bem, isso é relativamente fácil, graças ao bom trabalho do [Time Acidanthera](https://github.com/acidanthera/OpenCorePkg) com macrecovery_

> [!NOTE]
> _Evite imagens distribuídas na internet._
> _Este processo não usará uma imagem completa do macOS, mas sim uma imagem de recovery. Ele baixará tudo dos servidores da Apple que será usado para instalar o macOS no seu PC/Notebook_

#### _Requisitos:_
- _Pen drive USB ou SSD externo com pelo menos 2 GB de espaço disponível_

- _EFI compatível com hardware_

> [!NOTE]
> _Certifique-se de que seu EFI esteja configurado corretamente para permitir acesso à Internet. Isso é um requisito, pois a recuperação baixará o macOS em tempo real dos servidores da Apple_

- _Obviamente, acesso à internet_
- _Baixe a pasta [macrecovery](https://github.com/Gilberto-Mascena/How-to-create-a-macOS-installer-without-a-Mac/releases)_
- _**Windows** ou **Linux**_
- _[Python 3](https://www.python.org/downloads/) instalado na máquina_

<a name="ancora"></a>

## _Navegação por tópicos_

- _**Passo 1**_
- [_No Windows_](#ancora1)
- [_No Linux_](#ancora2)
- _**Passo 2**_
- [_No Windows_](#ancora3)
- [_No Linux_](#ancora4)
- [*Agradecimentos*](#ancora5)
- [*Licença* ](#ancora6)

## _Passo 1_

### _Instalando Python_

<a id="ancora1"></a>

<details><summary><h4>No Windows 👀</h4></summary>

- _Ao instalar no **Windows** marque a opcão `Add Python to PATH`_

<div align="center">
    <img src="./assets/miscellany/path-python.png" width="600">
</div>

- _Verificando a instalação:_ 
    - _No **Windows**, abra um prompt ou terminal e execute o comando abaixo_

```
python --version
```
- _Se retornar algo como `python 3.x.x`, a instalação foi bem-sucedida e podemos ir para o passo 2_

<div>
    <img src="./assets/windows/python-version-win.png">
</div>

[Top](#ancora)
</details>

<a id="ancora2"></a>

<details><summary><h4>No Linux 👀</h4></summary>

- _No **Linux**, o Ubuntu por exemplo, geralmente vem com o Python instalado, então verifique primeiro se você o tem instalado_

    - _Verificando a instalação:_
        - _No **Linux** abra um terminal e execute o comando abaixo_

```
python --version
```

#### _Ou_

```
python3 --version
```

- _Se retornar algo como `python 3.x.x`, o python já está instalado, podemos ir para o passo 2_

<div>
    <img src="./assets/linux/python-version.png">
</div>


- _Caso contrário, para **Debian** e derivados, no terminal execute o comando abaixo_

```
sudo apt update && sudo apt upgrade -y
```

- _Digite a senha do usuário para atualizar os pacotes e instalar as atualizações no sistema, após o processo ser concluído, execute o comando abaixo_

```
sudo apt install python3 -y
```

- _Digite a senha do usuário para instalação, após a conclusão feche o terminal e abra-o novamente. Por fim, verifique a instalação executando o comando abaixo novamente_

```
python --version
```

#### _Ou_

```
python3 --version
```

- _Se retornar algo como `python 3.x.x`, o python já está instalado, podemos ir para o passo 2_

<div>
    <img src="./assets/linux/python-version.png">
</div>

[Top](#ancora)
</details>


## _Passo 2_

### _Criando instalador_

<a id="ancora3"></a>

<details><summary><h4>No Windows 👀</h4></summary>

1. [_Baixar o macrecovery_](https://github.com/Gilberto-Mascena/How-to-create-a-macOS-installer-without-a-Mac/releases)
2. _Formatar a unidade flash USB em FAT32_
3. _Abrir a pasta macrecovery baixada anteriormente_

<div>
    <img src="assets/windows/content-recovery-win.png">
</div>

4. _Abrir o arquivo `recovery_urls.txt`_

<div>
    <img src="./assets/windows/URLs-win.png">
</div>

5. _Conforme destacado no título acima, a seção em vermelho baixa a recuperação do macOS Ventura, apenas copiar. O mesmo vale para outras versões._

6. _Abra um terminal na pasta macrecovery e digite `python`, pressione espaço e cole a url copiada. Pressione Enter e aguarde_

<div>
    <img src="./assets/windows/download macos-win.png">
</div>

7. _Esta tela mostra que o download foi concluído com sucesso._

<div>
    <img src="./assets/windows/download complete-win.png">
</div>

8. _Volte para a pasta do macrecovery e observe que agora temos a pasta `com.apple.recovery.boot`. Copie a pasta para o pendrive previamente formatado_

<div>
    <img src="./assets/windows/folder-recovery-win.png">
</div>

9. _Agora copie seu `EFI` para o pendrive também_ 
    - _A estrutura de pastas e arquivos deve ficar como nas telas abaixo_

<div>
    <img src="./assets/windows/folders-on-the-pen-win.png">

- _Arquivos que compõem a pasta `com.apple.recovery.boot`_

    <img src="./assets/windows/files-recovery-win.png">

- _Arquivos que compõem a pasta `EFI`_

<   img src="./assets/windows/oc-folders-win.png">

- _Arquivos que compõem a pasta `oc`_

    <img src="./assets/windows/EFI-folders-win.png">
</div>

10. 🎉 _Finalmente temos um pendrive pronto para instalar o macOS escolhido em `recovery_urls.txt`_



[Top](#ancora)
</details>

<a id="ancora4"></a>

<details><summary><h4>No Linux 👀</h4></summary>

1. [_Baixar o macrecovery_](https://github.com/Gilberto-Mascena/How-to-create-a-macOS-installer-without-a-Mac/releases)
2. _Formatar a unidade flash USB em FAT32_
3. _Abrir a pasta macrecovery baixada anteriormente_

<div>
<img src="./assets/linux/content-macrecovery.png">
</div>

4. _Abrir o arquivo `recovery_urls.txt`_

<div>
<img src="./assets/linux/URLs.png">
</div>

5. _Conforme destacado no título acima, a seção em vermelho baixa a recuperação do macOS Ventura e apenas a copia. O mesmo vale para outras versões._

6. _Abrir um terminal na pasta macrecovery e digitar `python3`, pressionar espaço e colar a url copiada. Pressione Enter e aguarde_

<div>
<img src="./assets/linux/download-recovery.png">
</div>

7. _Esta tela mostra que o download foi concluído com sucesso._

<div>
<img src="./assets/linux/download-complete.png">
</div>

8. _Volte para a pasta macrecovery e observe que agora temos a pasta `com.apple.recovery.boot`. Copie a pasta para o pendrive formatado anteriormente_

<div>
<img src="./assets/linux/folder-recovery.png">
</div>

9. _Agora copie seu `EFI` para o pendrive também_
- _A estrutura de pastas e arquivos deve ficar como nas telas abaixo_

<div>
<img src="./assets/linux/folders-on-the-pendrive.png">

- _Arquivos que compõem a pasta `com.apple.recovery.boot`_

<img src="./assets/linux/files-recovery.png">

- _Arquivos que compõem a pasta `EFI`_

<img src="./assets/linux/OC-folders.png">

- _Arquivos que compõem a pasta `oc`_

<img src="./assets/linux/EFI-folders.png">
</div>

10. 🎉 _Finalmente temos um pendrive pronto para instalar o macOS escolhido em `recovery_urls.txt`_

[Top](#ancora)
</details>

<a id="ancora5"></a>

## _Agradecimentos_

- [*Acidanthera Team*](https://github.com/acidanthera)
- [*CorpNewt*](https://github.com/corpnewt)
- [*Dortania*](https://dortania.github.io/OpenCore-Install-Guide/config.plist/comet-lake.html#platforminfo)
- [*Dicas do Mateus*](https://www.youtube.com/c/DicasdoMateus)
- [*Gabriel Luchina*](https://www.youtube.com/c/gabrielluchina)
- *E outros*

[Top](#ancora)
</details>

<a id="ancora6"></a>

## _Licença_

[_Licença MIT_](./LICENSE.md)(_MIT_)

### Gilberto | Dev _2024_

[Top](#ancora)
</details>