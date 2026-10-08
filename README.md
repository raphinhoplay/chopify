<p align="center">
  <img src="assets/banner.svg" alt="Chopify" width="880">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.11+-3776AB?logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/100%25-Local-08d9d6" alt="Local">
  <img src="https://img.shields.io/badge/APIs_Pagas-zero-ff2e63" alt="Sem APIs pagas">
  <img src="https://img.shields.io/badge/ffmpeg-potente-007808?logo=ffmpeg&logoColor=white" alt="ffmpeg">
  <img src="https://img.shields.io/badge/OpenCV-YuNet-5C3EE8?logo=opencv&logoColor=white" alt="OpenCV">
  <img src="https://img.shields.io/badge/Windows-11-0078D6?logo=windows&logoColor=white" alt="Windows">
</p>

<p align="center"><b>Cole um link do YouTube &#8594; receba clipes pontuados e legendados (16:9 ou 9:16) &#8212; 100% na sua própria máquina.</b></p>

---

**Chopify é uma alternativa gratuita, open-source e totalmente local ao Opus Clip, Vizard, Klap, 2Short e Submagic.** Ele transforma automaticamente vídeos longos &#8212; como vídeos do YouTube, podcasts, entrevistas e webinars &#8212; em clipes curtos prontos para publicação nos formatos **16:9, 9:16 (vertical) ou 1:1**, com pontuação de viralidade por IA, enquadramento automático com rastreamento facial e legendas palavra por palavra embutidas. Tudo roda **100% na sua própria máquina**: sem assinatura, sem upload para a nuvem e sem chaves de API.

> [!TIP]
> **Novidade na v1.1** &#8212; a saída padrão agora é **16:9 em tela cheia** (sem recorte). Adicione `--aspect 9:16` para vertical ou `--aspect 1:1` para quadrado, e **cada clipe salva automaticamente um poster PNG** ao lado do `.mp4`.

## Demonstração

<p align="center"><img src="assets/demo.gif" alt="Clipe 16:9 com legendas palavra por palavra embutidas" width="640"></p>

## Como funciona

<p align="center">
  <img src="assets/pipeline.svg" alt="Fluxo de trabalho" width="980">
</p>

## Funcionalidades

- **Pontuação de viralidade por IA** &#8212; cada segmento é avaliado em gancho, choque, humor, controvérsia, insight, emoção, energia e arco completo; apenas clipes com **nota 8+/10** são mantidos.
- **Transcrição local** &#8212; faster-whisper com timestamps em nível de palavra. Nada sai do seu PC.
- **Saída em múltiplos formatos** &#8212; 16:9 (padrão, tela cheia), 9:16 (com auto-enquadramento com rastreamento de falante via OpenCV YuNet, ajuste no corte e proteção de borda) ou 1:1.
- **Poster PNG por clipe** &#8212; uma miniatura pronta salva ao lado de cada clipe.
- **Legendas palavra por palavra** &#8212; estilo CapCut em negrito, embutidas com ffmpeg.
- **Zero APIs pagas, zero nuvem** &#8212; yt-dlp + faster-whisper + ffmpeg + OpenCV.
- **O conteúdo define a quantidade** &#8212; um vídeo de 1 hora pode gerar 2 clipes ou 20.

## Chopify vs. as ferramentas pagas

O Chopify faz o essencial que esses produtos por assinatura fazem &#8212; **clipes com pontuação por IA, auto-enquadramento para 9:16 e legendas palavra por palavra embutidas** &#8212; só que roda **gratuitamente, na sua própria máquina e é totalmente open-source**.

| Produto | Preço | Execução | Open source |
| --- | --- | --- | --- |
| **Chopify** | **Gratuito** | **Local (seu PC)** | **MIT** |
| [Opus Clip](https://www.opus.pro) | Assinatura paga | Nuvem | Não |
| [Vizard.ai](https://vizard.ai) | Assinatura paga | Nuvem | Não |
| [Klap](https://klap.app) | Assinatura paga | Nuvem | Não |
| [2Short.ai](https://2short.ai) | Freemium + pago | Nuvem | Não |
| [Munch](https://www.getmunch.com) | Assinatura paga | Nuvem | Não |
| [Spikes Studio](https://spikes.studio) | Freemium + pago | Nuvem | Não |
| [Submagic](https://www.submagic.co) | Assinatura paga | Nuvem | Não |
| [SendShort](https://sendshort.ai) | Assinatura paga | Nuvem | Não |

<sub>Produtos e marcas são de seus respectivos proprietários; preços e recursos podem mudar com o tempo. A comparação cobre apenas o fluxo de vídeo longo para clipes curtos.</sub>

## Requisitos

- Windows, Python 3.11+
- `ffmpeg` + `ffprobe` no PATH &#8212; `winget install Gyan.FFmpeg`
- `deno` no PATH (para resolver desafios JS do yt-dlp) &#8212; `winget install DenoLand.Deno`

## Instalação

```bash
python -m venv .venv
.venv\Scripts\python -m pip install -r requirements.txt