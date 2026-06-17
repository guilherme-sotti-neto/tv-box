# UNIVERSIDADE TECNOLÓGICA FEDERAL DO PARANÁ - CAMPUS PONTA GROSSA (UTFPR-PG)

## DEPARTAMENTO ACADÊMICO DE ELETRÔNICA - CAMPUS PONTA GROSSA (DAELE-PG)

---

## PROCEDIMENTO OPERACIONAL PADRÃO 

### Assunto: Instalação de Imagem Android (TV Box RPC) e Configuração do Mural Digital AbleSign via APK

### 1. OBJETIVO

Descrever as etapas para a substituição do sistema operacional de fábrica das TV Boxes com processador RockChip322x por uma imagem Android otimizada, e detalhar a instalação manual do aplicativo de sinalização digital AbleSign diretamente pelo navegador do dispositivo.

---

### PARTE 1: INSTALAÇÃO DO SISTEMA ANDROID (VIA MULTITOOL)

#### 1.1 Pré-requisitos

* Cartão Micro SD (Mínimo de 4GB).
* Computador para gravação da imagem.
* Software de gravação de imagens (Recomendado: **balenaEtcher**, Rufus ou Win32 Disk Imager).
* Imagem do **Utilitário Multitool** (arquivo `[multitool.img.xz](https://drive.google.com/file/d/1WSdFRLrBlIBq5H8GJqeBilelnq-wJyTK/view?usp=drive_link)`).
* Imagem Android otimizada ([EducaBox](https://github.com/educabox/educabox)) correspondente ao seu modelo de TV Box (arquivos compactados disponibilizados no repositório).

#### 1.2 Download e Instalação do balenaEtcher (No Computador)
O balenaEtcher é o software homologado para gravar a imagem do sistema no cartão SD de forma segura, evitando corrupção de dados.
*Em seu computador, abra o navegador e acesse o site oficial: [https://etcher.balena.io/](https://etcher.balena.io/)
*Clique no botão verde Download Etcher.
*A página rolará até a lista de downloads. Selecione a versão correspondente ao seu sistema operacional (Windows, macOS ou Linux). Nota: Para usuários Windows, recomenda-se a versão "Installer" (Instalador).
*Aguarde a conclusão do download e execute o arquivo baixado (ex: balenaEtcher-Setup.exe).
*Na janela de instalação, clique em Concordo (I Agree) para aceitar os termos de licença.
*A instalação é rápida e silenciosa. Ao finalizar, o atalho será criado na área de trabalho e o balenaEtcher será aberto automaticamente, pronto para uso.

#### 1.3 Preparação do Cartão SD (No Computador)

1. Conecte o cartão Micro SD ao computador.
2. Abra o software **balenaEtcher**.
3. Selecione a imagem do utilitário `[multitool.img.xz](https://drive.google.com/file/d/1WSdFRLrBlIBq5H8GJqeBilelnq-wJyTK/view?usp=drive_link)`.
4. Selecione a unidade correspondente ao seu cartão SD e clique em **Flash**.
5. Aguarde a finalização. Remova o cartão SD e **insira-o novamente** no computador.
6. O cartão montará uma partição visível. Acesse a pasta `/backup` dentro dessa partição.
7. Copie o arquivo da imagem Android (EducaBox) compactada para dentro da pasta `/backup`.
8. Ejete o cartão SD com segurança.

#### 1.4 Instalação na TV Box RPC

1. Com a TV Box RPC **desligada** da energia, insira o cartão SD preparado.
2. Ligue a TV Box à energia.
* *Nota:* Dependendo do modelo TV Box será necessário desconectar da energia, inserir um clipe de papel na entrada AV (para pressionar o botão oculto de *update*), ligar a energia e solte o botão após 3 segundos.


3. O utilitário **Multitool** será carregado. Conecte um teclado USB à TV Box.
4. **Formatação (Erase):**
* Use as setas do teclado para selecionar `Erase flash` e pressione **Enter**.
* Selecione o armazenamento interno (`eMMC`) da TV Box e confirme. Uma tela de sucesso será exibida. Pressione **Enter** para voltar.


5. **Instalação (Restore):**
* Selecione a opção `Restore flash` e pressione **Enter**.
* Escolha novamente a unidade interna (`eMMC`).
* Selecione a imagem Android que você copiou para a pasta `/backup` do SD Card.
* Aguarde o progresso chegar a 100%.


6. Selecione `Shutdown` para desligar.
7. **Remova o cartão SD** e ligue a TV Box novamente. O novo sistema Android Educabox será inicializado (pode demorar alguns minutos no primeiro boot).

---

### PARTE 2: INSTALAÇÃO E CONFIGURAÇÃO DO ABLESIGN VIA NAVEGADOR

A imagem Android recém-instalada já possui aplicativos essenciais pré-instalados, como **Chrome**, **Opera** e um **File Explorer**.

#### 2.1 Download e Instalação do APK

1. Na tela inicial do Android, conecte a TV Box RPC à rede Wi-Fi ou cabo de rede (Ethernet).
2. Abra o navegador pré-instalado (**Chrome** ou **Opera**).
3. Na barra de endereços, digite o site oficial: `[https://www.ablesign.tv/](https://www.ablesign.tv/)`
4. Navegue até o menu superior e clique em **Downloads**.
5. Role a página até encontrar a opção **Android** e clique no botão para baixar o arquivo **APK**.
6. Aguarde o fim do download.
7. Abra o aplicativo **Explorer** (pré-instalado no sistema) e navegue até a pasta **Downloads**.
8. Selecione o arquivo `.apk` do AbleSign recém-baixado.
* *Nota:* Se o sistema emitir um alerta de segurança, clique em "Configurações" e ative a permissão **"Permitir desta fonte"** (Instalar apps desconhecidos).


9. Clique em **Instalar** e, ao finalizar, clique em **Abrir**.

#### 2.2 Vinculação do Dispositivo (Emparelhamento)

1. Ao abrir o AbleSign na TV Box RPC, ele exibirá um **Código de Emparelhamento (Pairing Code)** de 6 dígitos em tela cheia.
2. Vá para um computador comum e acesse o painel web: `[https://app.ablesign.tv/](https://app.ablesign.tv/)`
3. Faça o login com a conta de gerenciamento da sua instituição.
4. No menu lateral esquerdo, clique em **Screens** (Telas).
5. Clique no botão azul **Add Screen** (Adicionar Tela).
6. Preencha os dados:
* **Pairing Code:** Insira os 6 dígitos exibidos na tela da TV Box.
* **Screen Name:** Dê um nome de identificação padrão (Ex: `Mural_TVBox_Recepcao`).


7. Clique em **Save**. A TV Box atualizará automaticamente e estará pronta para receber as mídias.

#### 2.3 Configuração de Reprodução Contínua

1. No painel web (`app.ablesign.tv`), vá em **Media** para enviar suas imagens/vídeos.
2. Vá em **Playlists**, crie uma lista e adicione as mídias carregadas.
3. Volte em **Screens**, selecione a TV Box recém-adicionada e defina a Playlist que ela deve reproduzir.
4. **No aparelho RPC (Opcional, mas recomendado):** Utilizando o controle remoto, abra as configurações do aplicativo AbleSign na TV Box e certifique-se de que a opção *Start on Boot* (Iniciar ao ligar) está ativada. Dessa forma, caso falte energia, o mural digital voltará a funcionar automaticamente sem intervenção humana.
