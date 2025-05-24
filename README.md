# Git: Clonar, Editar e Enviar Alterações para o GitHub (Windows)

Este guia mostra como configurar o Git no Windows, clonar um repositório do GitHub, editar arquivos e enviar as alterações de volta via terminal.

---

## 🛠️ Pré-requisitos

- [Git para Windows](https://git-scm.com/download/win) instalado
- Conta no [GitHub](https://github.com/)
- Um repositório no GitHub (ou acesso a um existente)

---

## ✅ Passo 1: Abrir o  Terminal

No menu iniciar do Windows, digite **Terminal** ou **CMD** e abra o terminal.

---

## 🔧 Passo 2: Configurar nome de usuário e e-mail

O Git usa seu nome e e-mail para associar aos commits. Execute:

```
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@exemplo.com"
```
## 🔐 Passo 3: Configurar autenticação com chave SSH (opcional, mas recomendado)
 1. Gerar chave SSH:
    ```
    ssh-keygen -t ed25519 -C "seuemail@exemplo.com"
    ```
    Pressione ``Enter`` até finalizar (deixe o caminho padrão e passphrase vazia ou uma que você lembre).
    
 2. Adicionar chave ao ssh-agent:
    ```
    eval "$(ssh-agent -s)"
    ssh-add ~/.ssh/id_ed25519
    ```
 3. Copiar chave pública:
    ```
    clip < ~/.ssh/id_ed25519.pub
    ```

 4. Adicionar no GitHub:
    - Vá em GitHub > Settings > SSH and GPG keys > **New SSH Key**
    - Cole a chave copiada no campo "Key" e dê um nome

## 📥 Passo 4: Clonar o repositório
 o terminal, navegue até onde quer salvar o projeto:
 ```
 cd /c/Users/SeuUsuario/Documents/
 ```

 Clone o repositório com o comando:
 ```
 git clone git@github.com:DiegoSousaOliveira/clonando_repositoprio.git
 ```

 Entre na pasta clonada:
 ```
 cd clonando_repositoprio
 ```

## ✏️ Passo 5: Editar o arquivo
Use um editor de texto como VS Code ou o Bloco de Notas para editar arquivos do projeto.

Exemplo usando VS Code (caso esteja instalado):
```
code .
```

Edite o arquivo desejado e salve as alterações.

 - antes de alterar o arquivo main.py
   
![image](https://github.com/user-attachments/assets/2f446aac-8b5a-46f2-b282-fd6a088c5f7e)


 - depois de alterar o arquivo main.py
   
![image](https://github.com/user-attachments/assets/1b1e4211-8c8f-4a2d-ba85-d73ed1f86ea0)


## ✅ Passo 6: Verificar mudanças
Após salvar, volte ao terminal e veja as alterações:
```
git status
```
Você verá arquivos modificados em vermelho.

![image](https://github.com/user-attachments/assets/effbd704-c6ac-4876-ba99-40805ccdd469)


## ➕ Passo 7: Adicionar alterações para commit
```
git add main.py
```
Ou para adicionar tudo de uma vez:
```
git add .
```

## 📝 Passo 8: Fazer o commit das alterações
```
git commit -m "Mensagem explicando o que foi alterado"
```

## 🚀 Passo 9: Enviar para o GitHub (push)
Antes de enviar, é recomendado fazer um pull para evitar conflitos:
```
git pull origin main --rebase
```

Agora, envie as alterações:
```
git push origin main
```
Se estiver usando HTTPS e for solicitado, insira seu nome de usuário e token de acesso do GitHub.
Se estiver usando SSH e configurou corretamente, o push será feito automaticamente.
