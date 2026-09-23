# 🚀 Git e GitHub na Prática

Se você está começando na programação ou ainda não utiliza **Git e GitHub**, este guia apresenta de forma simples como configurar o Git, conectar sua máquina ao GitHub e versionar seu primeiro projeto.

Ter um repositório configurado é uma das práticas fundamentais no desenvolvimento de software, principalmente para **controlar versões, manter o histórico do código e trabalhar em equipe**.

---

# 📥 Instalando o Git

Faça o download do Git pelo site oficial:

https://git-scm.com/downloads

Após a instalação, teremos acesso ao **Git Bash**, que será utilizado durante este tutorial.

---

# 🤔 Git e GitHub são a mesma coisa?

**Não.** Apesar de trabalharem juntos, Git e GitHub possuem funções diferentes.

**Git** é um sistema de controle de versão. Ele registra o histórico das alterações realizadas nos arquivos de um projeto, permitindo acompanhar o que mudou, quem realizou determinada alteração e até recuperar versões anteriores.

**GitHub** é uma plataforma online utilizada para hospedar repositórios Git. Além de armazenar projetos, oferece recursos para colaboração entre desenvolvedores, como Pull Requests, Issues, Code Review e gerenciamento de projetos.

De forma simples:

> **Git controla as versões do seu código. GitHub armazena e facilita a colaboração nesses repositórios.**

![Comparativo Git e GitHub](https://github.com/freesheets/GitTutorial/assets/169274014/387c7a2c-f0ce-4d14-888a-9bfd62a69d19)

---

# 🔄 Para que serve o Git?

Em projetos profissionais, é comum que várias pessoas trabalhem no mesmo código. Por isso, apenas compartilhar os arquivos não é suficiente: precisamos controlar **quem alterou, o que foi alterado e quando determinada mudança aconteceu**.

É justamente aí que entra o Git.

As alterações podem ser registradas através de **commits**, que representam pontos específicos no histórico do projeto.

Uma maneira simples de entender é pensar nos commits como **Save Points de um jogo**:

> 💡 Cada commit registra um estado do projeto. Caso alguma alteração cause problemas, é possível consultar e recuperar versões anteriores do código.

Isso permite comparar mudanças, encontrar bugs, recuperar código e acompanhar toda a evolução do projeto.

<img width="1710" height="920" alt="image" src="https://github.com/user-attachments/assets/8a7047ba-f3e8-46d5-b683-f447ec023dc3" />


---

# ⚙️ Configurando o Git

Antes de utilizar o GitHub, precisamos realizar algumas configurações.

## 1. Abra o Git Bash

Após instalar o Git, clique com o botão direito na área de trabalho

**Open Git Bash Here**

![Abrindo Git Bash](https://github.com/freesheets/GitTutorial/assets/169274014/7e695477-f962-447f-9d6f-220c04c723b3)

---

## 2. Configure seu nome e e-mail

O Git registra o autor de cada commit. Configure seu nome e o e-mail utilizado no GitHub:

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu email@exemplo.com"
```

> **Importante:** utilize preferencialmente o mesmo e-mail configurado em sua conta do GitHub.

---

# 🔑 Configurando uma chave SSH

A chave SSH permite autenticar sua máquina no GitHub de forma segura.

## 3. Gere sua chave SSH

No Git Bash, execute:

```bash
ssh-keygen -t rsa -b 4096 -C "seuemail@exemplo.com"
```
Isso criará uma nova chave SSH utilizando seu e-mail como identificação.

![SSH Key](https://github.com/freesheets/GitTutorial/assets/169274014/690c8e73-9009-4502-8849-3a733926bf57)

Quando aparecer:

```text
Enter a file in which to save the key
```

pressione **Enter** para utilizar o local padrão.

![Local da chave SSH](https://github.com/freesheets/GitTutorial/assets/169274014/85c203c3-ecca-405b-8b40-cc220c48cb38)

Em seguida, você poderá definir uma senha para proteger sua chave ou pressionar **Enter** para continuar sem senha.

---

## 4. Copie sua chave pública

No Windows, normalmente ela estará localizada em:

```text
C:\Users\SeuUsuario\.ssh\
```

![Arquivo SSH](https://github.com/freesheets/GitTutorial/assets/169274014/9dfb6f5f-9151-4524-b24b-cee57bd5f988)

Procure pelo arquivo id_rsa.pub  ← 🔑 PÚBLICA copie todo o conteúdo.

<img width="817" height="229" alt="image" src="https://github.com/user-attachments/assets/d4383d71-7409-40ba-a2ec-b4bdd5458fac" />


---

## 5. Acesse as configurações do GitHub

Abra sua conta no GitHub, clique na sua foto de perfil e acesse:

**Settings**

![GitHub Settings](https://github.com/freesheets/GitTutorial/assets/169274014/0330d636-a8dd-47c8-9e31-7440ef7d69bc)

---

## 6. Acesse SSH and GPG Keys

Dentro das configurações, selecione:

**SSH and GPG keys**

![SSH and GPG Keys](https://github.com/freesheets/GitTutorial/assets/169274014/80c9a149-367a-4b02-8867-6b476e92287e)

---

## 7. Adicione sua chave

Clique em **New SSH key**, informe um título para identificar seu computador e cole sua chave pública no campo **Key**.

![Adicionar SSH Key](https://github.com/freesheets/GitTutorial/assets/169274014/84c4831e-15c1-4f97-8a42-1acd022a092e)

Pronto! Sua máquina poderá se autenticar no GitHub utilizando SSH.

---

# 📦 Como criar um repositório e enviar para o GitHub

Agora podemos versionar um projeto e enviá-lo para o GitHub.

## 1. Abra o Git Bash na pasta do projeto

Entre na pasta que deseja versionar e abra o **Git Bash**.

![Abrindo projeto](https://github.com/freesheets/GitTutorial/assets/169274014/1981bc8e-7904-4f61-ad5a-f3cd039cab45)

---

## 2. Inicialize o repositório

Execute:

```bash
git init
```

Esse comando transforma a pasta atual em um repositório Git.

---

## 3. Adicione os arquivos

Para adicionar um arquivo específico:

```bash
git add nome-do-arquivo
```

Para adicionar todas as alterações:

```bash
git add .
```

Os arquivos adicionados ficam na **Staging Area**, aguardando a criação do próximo commit.

---

## 4. Crie seu primeiro commit

Agora registre as alterações:

```bash
git commit -m "sua mensagem de commit aqui"
```
O `-m` permite informar uma mensagem descrevendo o que foi realizado naquele commit.

---

## 5. Visualize o histórico

Para visualizar os commits realizados:

```bash
git log
```

Uma versão mais resumida também pode ser visualizada com:

```bash
git log --oneline
```

## 6. Crie o repositório no GitHub

No GitHub, selecione **New repository**, escolha o nome do projeto e crie o repositório.

![Criando repositório](https://github.com/freesheets/GitTutorial/assets/169274014/c1408dbc-127f-4393-9d74-600b73178c29)

Caso seu projeto local já possua arquivos, você pode criar o repositório **sem adicionar README, `.gitignore` ou License**, simplificando o primeiro envio.

![Configuração do repositório](https://github.com/freesheets/GitTutorial/assets/169274014/0f2a63f9-1a64-4cb6-88fd-1144085677e8)

---

## 7. Conecte o projeto ao GitHub

Após criar o repositório, copie o endereço **SSH** fornecido pelo GitHub.

Execute:

```bash
git branch -M main
git remote add origin git@github.com:SEU-USUARIO/SEU-REPOSITORIO.git
git push -u origin master
```

![Enviando projeto para GitHub](https://github.com/freesheets/GitTutorial/assets/169274014/c72cadc0-4381-4ef1-8e96-2d3be1cc85d6)

Pronto! 🎉

Seu projeto local agora está versionado com Git e conectado ao GitHub.

---

# 🧰 Comandos Git essenciais

| Comando                    | Função                                           |
| -------------------------- | ------------------------------------------------ |
| `git init`                 | Inicializa um repositório Git                    |
| `git status`               | Mostra o estado atual dos arquivos               |
| `git add .`                | Adiciona todas as alterações à Staging Area      |
| `git commit -m "mensagem"` | Cria um novo commit                              |
| `git log`                  | Exibe o histórico de commits                     |
| `git log --oneline`        | Exibe o histórico resumido                       |
| `git branch`               | Lista as branches                                |
| `git switch nome-branch`   | Troca de branch                                  |
| `git pull`                 | Baixa e integra alterações do repositório remoto |
| `git push`                 | Envia commits para o repositório remoto          |
| `git clone URL`            | Clona um repositório existente                   |
| `git remote -v`            | Exibe os repositórios remotos configurados       |

---

# 🔁 Fluxo básico do dia a dia

Depois que o projeto estiver configurado, o fluxo mais comum será:

```bash
git pull
```

Faça suas alterações no código e depois:

```bash
git status
git add .
git commit -m "Descrição da alteração"
git push
```

De forma resumida:

```text
Código alterado
      ↓
   git add
      ↓
  git commit
      ↓
   git push
      ↓
    GitHub
```

## 🎯 Conclusão

Com esses conceitos você já consegue utilizar o fluxo básico de **Git + GitHub** para versionar seus projetos.

Conforme evoluir, vale estudar também **branches, merge, pull requests, conflitos, `.gitignore`, Git Flow e Conventional Commits**.
