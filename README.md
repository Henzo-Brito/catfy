# 🎵 Catfy
<img width="336" height="336" alt="catfy" src="https://github.com/user-attachments/assets/bfc004f8-ff4a-441f-be29-844fea716672" />

Um player de música mobile inspirado no Spotify, construído com React Native e Expo. O app toca músicas de verdade, com controles completos de reprodução, navegação por playlists e um mini player que aparece em qualquer tela.

---

## Telas do app

<div align="center">

| Home | Buscar | Sua Biblioteca |
|:----:|:------:|:--------------:|
| <img width="220" src="https://github.com/user-attachments/assets/1c96d0df-9044-490c-a93e-c8364505f6bc" /> | <img width="220" src="https://github.com/user-attachments/assets/6cf0bd38-0b90-4b05-8fe3-a0568852c38c" /> | <img width="220" src="https://github.com/user-attachments/assets/26a64e7b-1b5e-444a-ab81-9faf94217667" />|


| Detalhes da Playlist | Player da Música | Busca Expandida |
|:--------------------:|:----------------:|:---------------:|
| <img width="220" src="https://github.com/user-attachments/assets/da6f7595-ade7-4cb7-903f-fd78731a3678" /> | <img width="220" src="https://github.com/user-attachments/assets/84d2baad-3047-4ba4-8e3c-2c4fdf45d09b" /> | <img width="220" src="https://github.com/user-attachments/assets/2c862e95-4bbd-4422-ae82-ebb6e9b5a4ac" />
|

</div>

---

## Sobre o projeto

O Catfy é um app de música para Android e iOS com uma seleção curada de 22 faixas da música brasileira — MPB, Bossa Nova, Samba e Soul — organizadas em playlists. O objetivo foi recriar a experiência de uso do Spotify: visual escuro, navegação fluida por abas e reprodução de áudio nativa.

---

## Funcionalidades

- **Reprodução de áudio real** — as músicas são arquivos `.mp3` embutidos no app, tocados via `expo-audio`
- **Player completo** — barra de progresso com marcador arrastável, tempo atual e total, controles de play/pause, próxima e anterior
- **Mini player flutuante** — aparece sobre todas as telas enquanto uma música está tocando, com controles rápidos e acesso ao player completo
- **Playlists** — duas playlists com músicas independentes; ao abrir uma playlist, o play inicia a fila inteira
- **Navegação por abas** — três seções principais: Home, Buscar e Sua Biblioteca
- **Tela de busca** — campo de pesquisa com lista de todas as músicas disponíveis
- **Tela da biblioteca** — lista todas as playlists salvas com acesso rápido
- **Filtros na home** — chips clicáveis para filtrar por Tudo, Música ou Podcasts
- **Fila de reprodução** — ao tocar uma playlist, a fila é definida automaticamente para navegar entre as faixas com os botões anterior/próxima

---

## Telas

| Tela | Descrição |
|------|-----------|
| **Home** | Playlists recentes, seções de artistas, álbuns e mixes em scroll horizontal |
| **Buscar** | Barra de busca e grade de músicas por estilo |
| **Sua Biblioteca** | Lista de playlists do usuário |
| **Detalhes da Playlist** | Capa, nome, botão play/shuffle e lista de faixas |
| **Detalhes da Música** | Capa grande, player com barra de progresso e controles |
| **Busca Expandida** | Campo de texto com histórico de músicas recentes |

---

## Músicas

O app vem com 22 faixas embutidas:

| Artista | Músicas |
|---------|---------|
| Djavan | Flor do Medo, Pétala, Samurai (feat. Stevie Wonder), Vive |
| Adoniran Barbosa | Bom Dia Tristeza, Iracema |
| Tom Jobim / Stan Getz | Corcovado (Quiet Nights Of Quiet Stars) |
| Jorge Vercillo | Devaneio, Melhor Lugar |
| Skank | Esquecimento |
| IVYSON | Girassol - Acústico |
| Tim Maia | Lamento, Primavera (Vai Chuva) |
| Jorge Ben Jor | Me Chamando de Paixão |
| Baco Exu do Blues | Me Desculpa Jay-Z - Remix |
| Arlindo Cruz | O Que É o Amor, Será que é amor |
| Onze:20 | Pra Você |
| Cazuza / Bebel Gilberto | Preciso Dizer Que Te Amo |
| Seu Jorge | São Gonça, Tive Razão - 2024 Remaster |
| Tyler The Creator | Like Him |

---

## Tecnologias

| Tecnologia | Uso |
|------------|-----|
| [React Native](https://reactnative.dev/) | Base do app |
| [Expo](https://expo.dev/) | Plataforma e ferramentas de build |
| [Expo Router](https://expo.github.io/router/) | Navegação baseada em arquivos |
| [expo-audio](https://docs.expo.dev/versions/latest/sdk/audio/) | Reprodução dos arquivos de áudio |
| [expo-linear-gradient](https://docs.expo.dev/versions/latest/sdk/linear-gradient/) | Gradientes nas telas de música e playlist |
| [lucide-react-native](https://lucide.dev/) | Ícones do player e da navegação |
| [react-native-reanimated](https://docs.swmansion.com/react-native-reanimated/) | Animações |
| [react-native-safe-area-context](https://github.com/th3rdwave/react-native-safe-area-context) | Margens seguras em iOS e Android |
| [TypeScript](https://www.typescriptlang.org/) | Tipagem estática |
| Context API | Estado global da reprodução |

---

## Estrutura do projeto

```
src/
├── app/                    # Rotas do app (Expo Router)
│   ├── (tabs)/             # Abas principais
│   │   ├── index.tsx       # Home
│   │   ├── search.tsx      # Buscar
│   │   └── library.tsx     # Sua Biblioteca
│   ├── music/[id].tsx      # Tela de detalhes da música
│   ├── playlist/[id].tsx   # Tela de detalhes da playlist
│   ├── search/search.tsx   # Busca expandida
│   └── _layout.tsx         # Layout raiz com o MiniPlayer
│
├── components/             # Componentes reutilizáveis
│   ├── miniPlayer/         # Mini player flutuante global
│   ├── music/              # Header, player e barra de progresso da tela de música
│   ├── playlist/           # Player e lista de faixas da tela de playlist
│   ├── search/             # Barra de busca e lista de recentes
│   └── ...                 # Album, Section, Filter, MusicMini, etc.
│
├── contexts/
│   └── music.context.tsx   # Estado global: faixa atual, play/pause, progresso, fila
│
├── db/
│   ├── Playlists.ts        # Dados das faixas e playlists (fonte de verdade)
│   └── setPlaylists.tsx    # Funções que montam os componentes a partir dos dados
│
├── constants/
│   └── styles.constant.tsx # Paleta de cores do app
│
├── tools/
│   └── formatTime.tsx      # Formata segundos em mm:ss
│
└── assets/
    ├── images/             # Capas dos artistas, playlists e ícone do app
    └── musics/             # Arquivos .mp3 embutidos
```

---

## Download

O APK mais recente está disponível para instalação direta no Android:

**[⬇️ Baixar APK](https://expo.dev/artifacts/eas/s_-OfwtNOll7uDBfMBUYphFSC2dXHtR6ze3o4tDnJ_w.apk)**

> Para instalar, habilite a opção **"Instalar de fontes desconhecidas"** nas configurações do seu Android.

---

## Como executar

**Pré-requisitos:** Node.js, Yarn e o aplicativo [Expo Go](https://expo.dev/client) no celular.

```bash
# Clone o repositório
git clone <url-do-repositorio>
cd Spotify

# Instale as dependências
yarn install

# Inicie o servidor de desenvolvimento
yarn start
```

Escaneie o QR code com o Expo Go (Android) ou com a câmera (iOS) para abrir o app.

Para rodar direto em um emulador:

```bash
yarn android   # emulador Android
yarn ios       # simulador iOS
```

---

## Como funciona a reprodução

O estado de reprodução fica em um `MusicContext` que envolve todo o app. Ele expõe a faixa atual, se está tocando, o progresso em tempo real (atualizado a cada 500ms), a fila e as funções `play`, `pause`, `resume`, `next` e `prev`.

Qualquer componente pode chamar `useMusic()` para acessar ou controlar a reprodução. O MiniPlayer usa esse mesmo contexto para exibir a faixa tocando e os botões de controle em qualquer tela do app.

Ao iniciar uma playlist, a fila completa é carregada no contexto. Os botões de próxima e anterior navegam pelo índice da fila e redirecionam automaticamente para a tela da nova faixa.
