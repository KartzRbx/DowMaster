<div align="center">

<img src="https://github.com/user-attachments/assets/649fa98b-7cda-4a8c-a1f6-9d62e67a5fb9" width="128" alt="Ícone do DowMaster">

# DowMaster

**Baixe músicas, playlists, álbuns e vídeos de uma vez só: leve, rápido e bonito.**

YouTube · YouTube Music · Spotify · SoundCloud · Facebook · packs de sons

[![Última versão](https://img.shields.io/github/v/release/KartzRbx/DowMaster?label=vers%C3%A3o&color=FF6A3D)](https://github.com/KartzRbx/DowMaster/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/KartzRbx/DowMaster/total?label=downloads&color=FFB23F)](https://github.com/KartzRbx/DowMaster/releases)
![Windows](https://img.shields.io/badge/Windows-10%20%7C%2011-8B6CFF)
![Linux](https://img.shields.io/badge/Linux-x86__64-8B6CFF)
![Feito em Rust](https://img.shields.io/badge/feito%20em-Rust-1B1826)

### [⬇ Baixar a última versão](https://github.com/KartzRbx/DowMaster/releases/latest)

</div>

---

## ✨ O que ele faz

- **Vários de uma vez.** Cole quantos links quiser (um por linha) e a fila baixa até 8 ao mesmo tempo.
- **Spotify sem login.** Cole o link de uma música, álbum ou playlist. O DowMaster lê as faixas e busca cada uma no YouTube com a **mesma duração**, então você não recebe um show inteiro no lugar da música.
- **Busca por nome.** Escreva `Artista - Música` e ele encontra.
- **Pastas organizadas.** Separa por **artista**, **artista › álbum**, **playlist** ou deixa tudo junto.
- **Álbum inteiro num vídeo só?** Ele corta em faixas pelos capítulos ou pelas pausas entre as músicas.
- **Formatos:** MP3, M4A, OPUS, FLAC, WAV e MP4 (vídeo).
- **Qualidade:** de 128 kbps até **Original (máxima)**, sem perda extra na conversão. Vídeo de 360p até 4K.
- **MP4 que toca em tudo.** Até 1080p, ele prefere H.264 + AAC, que abre no iPhone, na TV e no WhatsApp.
- **Packs de sons.** Links diretos de `.zip`, `.wav` e `.mp3` são baixados, e o `.zip` é extraído sozinho.
- **Capa e metadados.** Título, artista, álbum e capa ficam gravados dentro do arquivo.
- **Não perde a fila.** Se o PC desligar, ao abrir de novo ele continua de onde parou.
- **Atualiza com um clique.** Quando sai versão nova, aparece o botão **"Atualizar agora"**, igual ao Discord.

## 📥 Instalação

### Windows

1. Baixe o **`DowMaster.zip`** na [página de versões](https://github.com/KartzRbx/DowMaster/releases/latest) e extraia.
2. Abra o **`DowMaster.exe`**. Não tem instalador.
3. Se aparecer *"O Windows protegeu o computador"*, clique em **Mais informações → Executar assim mesmo**. O aviso aparece porque o app não tem assinatura digital paga.
4. No app, clique em **Instalar componentes**. Ele baixa o yt-dlp e o FFmpeg (~100 MB) uma única vez.

### Linux

```bash
tar -xzf DowMaster-linux.tar.gz
cd DowMaster
sudo apt install ffmpeg xdg-desktop-portal   # Fedora: dnf · Arch: pacman
./instalar.sh                                # adiciona ao menu de aplicativos
```

Depois, abra o **DowMaster** pelo menu e clique em **Instalar componentes**.

## 🎧 Como usar

1. Cole os links ou nomes na aba **Baixar**. Também dá pra arrastar um `.txt` com links pra janela.
2. Escolha o **formato**, a **qualidade** e a **pasta**.
3. Clique em **Baixar** e acompanhe tudo na aba **Fila**.
4. O que terminou aparece na **Biblioteca**, com atalho pra abrir a pasta.

## ❓ Problemas comuns

| Problema | Solução |
|---|---|
| Facebook ou YouTube pedem login / erro de cookies | Em **Ajustes → Cookies do navegador**, escolha o navegador onde você está logado e **feche esse navegador** antes de baixar. O Firefox é o que funciona melhor. |
| O YouTube parou de baixar | **Ajustes → Atualizar yt-dlp**. O site muda com frequência. |
| O vídeo não abre no iPhone | Baixe em MP4 até 1080p. A versão atual já escolhe o formato compatível. |
| "Não achei no YouTube uma versão com a duração da faixa" | Essa música do Spotify não tem um vídeo parecido no YouTube. Tente buscar pelo nome. |

## 🎨 Visual

Layout inspirado em players de streaming, com paleta própria **"Ember Night"**: coral `#FF6A3D` e âmbar `#FFB23F` sobre preto-violeta `#07060C`.

## 🛠 Para desenvolvedores

Feito em **Rust** com [egui](https://github.com/emilk/egui). Para baixar e converter, usa o [yt-dlp](https://github.com/yt-dlp/yt-dlp) e o [FFmpeg](https://ffmpeg.org).

```bash
cargo build --release                                              # Windows
cargo zigbuild --release --target x86_64-unknown-linux-gnu.2.28    # Linux (via Zig)
.\publicar.ps1 1.0.1 "o que mudou"                                 # compila tudo e publica a versão
```

| Arquivo | Função |
|---|---|
| `src/app.rs` | telas, barra lateral e barra inferior |
| `src/downloader.rs` | fila, yt-dlp, separação de álbuns, retomada |
| `src/spotify.rs` | leitura de links do Spotify |
| `src/updater.rs` | atualização automática pelo GitHub Releases |
| `src/theme.rs` | paleta e componentes visuais |

---

<div align="center">
<sub>Baixe apenas conteúdo que você tem direito de usar. O Spotify é usado só para ler os nomes das faixas.</sub>
</div>
