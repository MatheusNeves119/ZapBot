# 🤖 Bot de Automação para WhatsApp com Python

Este projeto é um script de automação construído em Python que utiliza a biblioteca Selenium para controlar o WhatsApp Web, enviando uma imagem estática acompanhada de uma legenda personalizada para múltiplos contatos ou grupos listados em uma planilha do Excel.

O script foi desenvolvido com foco em "humanizar" as interações para minimizar o risco de bloqueio pela plataforma, incorporando pausas e variações aleatórias nas mensagens.
---

## ✨ Funcionalidades Principais

-   **Login Automatizado:** O script abre o navegador e aguarda o usuário escanear o QR Code para login.
-   **Leitura de Dados Externos:** Puxa a lista de contatos/grupos e as respectivas mensagens de uma planilha `Contatos.xlsx`.
-   **Envio de Mídia com Legenda:** Automatiza o processo de anexar uma imagem e adicionar uma legenda de texto com múltiplas linhas.
-   **Humanização e Anti-bloqueio:**
    -   Utiliza pausas com durações aleatórias entre as ações.
    -   Adiciona uma saudação aleatória no início de cada mensagem para evitar conteúdo duplicado.
    -   Implementa uma pausa longa e variável entre o envio para diferentes contatos/grupos.

---

## 🛠️ Tecnologias Utilizadas

-   **Python 3.11**
-   **Selenium:** Para automação e controle do navegador web.
-   **OpenPyXL:** Para leitura e manipulação da planilha do Excel (`.xlsx`).
-   **Pyperclip:** Para lidar com a área de transferência (Copiar/Colar), garantindo que mensagens com quebras de linha sejam enviadas corretamente.
-   **PyAutoGUI:** Utilizado para as pausas (`sleep`).

---

## 🚀 Como Executar o Projeto

Siga os passos abaixo para configurar e rodar o projeto na sua máquina.

### Pré-requisitos

-   [Python 3.8+](https://www.python.org/downloads/) instalado.
-   Navegador Google Chrome instalado.
-   [Git](https://git-scm.com/download/win) instalado.

### Guia de Instalação

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/seu-usuario/nome-do-seu-repositorio.git](https://github.com/seu-usuario/nome-do-seu-repositorio.git)
    cd nome-do-seu-repositorio
    ```

2.  **Crie e ative um ambiente virtual (recomendado):**
    ```bash
    python -m venv venv
    .\venv\Scripts\activate
    ```

3.  **Instale as dependências:**
    Crie um arquivo chamado `requirements.txt` na pasta do projeto com o seguinte conteúdo:
    ```txt
    selenium
    openpyxl
    pyperclip
    pyautogui
    ```
    Em seguida, instale as bibliotecas com o comando:
    ```bash
    pip install -r requirements.txt
    ```

### Configuração

Antes de rodar, você precisa preparar dois arquivos na pasta principal do projeto (estes arquivos são ignorados pelo `.gitignore` e não serão enviados para o GitHub):

1.  **`Contatos.xlsx`:** Uma planilha do Excel com duas colunas:
    -   **Coluna A:** O nome exato do contato ou grupo como está salvo no seu WhatsApp.
    -   **Coluna B:** A mensagem que você deseja enviar. Você pode usar quebras de linha normalmente dentro da célula.

2.  **`Foto_Tenis.jpeg`:** A imagem que o robô irá enviar. Você pode alterar o nome e a extensão do arquivo, mas lembre-se de atualizar a variável `imagem_para_enviar` no código.

### Execução

Com o ambiente virtual ativado e os arquivos de configuração prontos, basta executar o script no seu terminal:

```bash
python MsgZap.py
