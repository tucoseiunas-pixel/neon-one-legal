# NeonDeck 🃏✨

O **NeonDeck** é uma plataforma moderna e responsiva de jogos de cartas multiplayer, projetada com uma estética futurista "Neon/Dark Mode". O grande diferencial do projeto é o respeito absoluto à privacidade e à soberania de dados do usuário: o app funciona em uma arquitetura serverless (zero-knowledge), utilizando a infraestrutura do próprio usuário para salvar o progresso.

## 🚀 Tecnologias Utilizadas

* **Frontend:** React / Vite / TypeScript
* **Estilização & Animações:** Tailwind CSS / Framer Motion
* **Autenticação & Cloud Storage:** Google Cloud Platform (OAuth 2.0 & Google Drive API)
* **Deploy:** Vercel

## 🔒 Soberania de Dados & Arquitetura

Diferente das plataformas tradicionais, o **NeonDeck** não possui um banco de dados centralizado para armazenar dados sensíveis dos jogadores. 
* A autenticação é feita diretamente via Google Sign-In.
* O progresso do jogo, configurações e histórico são salvos de forma criptografada diretamente no próprio Google Drive do usuário, utilizando a pasta oculta `AppDataFolder` (`https://www.googleapis.com/auth/drive.appdata`).
* **Zero-Knowledge:** Nós não temos acesso, não coletamos e não armazenamos suas informações ou dados de jogo em servidores de terceiros.

## 🛠️ Como Jogar

Jogue diretamente pelo navegador ou baixe aplicativo em www.neondeck.com.br