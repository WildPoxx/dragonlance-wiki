Tutorial Completo: Como Gravar e Degravar Sessões de RPG no Zoom e Google Meet

🔹 Objetivo

Registrar as sessões de jogo de RPG em formato de áudio e convertê-las em texto automaticamente, com marcação de falas e organização por falante, para uso posterior na reconstrução narrativa.

☑️ Etapa 1: Como Gravar Sessões de RPG Online

A. Usando Zoom

Inicie a reunião como host.

Clique em Gravar e escolha Gravar na nuvem ou Gravar no computador.

Acesse: Configurações > Gravação.

Ative a opção “Gravar um arquivo de áudio separado para cada participante”.

Ao fim da sessão, Zoom gerará:

Um .mp4 com vídeo completo.

Múltiplos .m4a (um por jogador).

B. Usando Google Meet

Utilize uma conta Google Workspace com permissão para gravar.

Clique em Atividades > Gravação e inicie.

O arquivo será salvo no Google Drive do organizador, como .webm ou .mp4.

Se quiser separar o áudio por jogador, use um plugin como Fireflies.ai (ver abaixo).

🔹 Etapa 2: Transcrição Automática das Sessões

Opção 1: Otter.ai (Recomendado)

Vantagens: Reconhecimento automático de falantes, transcrição com timestamps, plano gratuito.

Passo a passo:

Acesse e crie uma conta.

Clique em Import e envie o arquivo .mp4 ou os .m4a separados.

Otter identifica os falantes com base no áudio e gera a transcrição.

Use Edit Speaker para nomear os jogadores.

Exporte em .txt, .pdf ou copie o texto diretamente.

Opção 2: Fireflies.ai (Plugin para Zoom e Google Meet)

Vantagens: Integra-se diretamente com Zoom/Meet, grava e transcreve automaticamente, reconhece falantes, cria destaques.

Passo a passo:

Acesse e crie uma conta.

Conecte sua conta Zoom ou Google Calendar.

Dê permissão para o bot Fireflies Notetaker participar das reuniões.

Durante o jogo, o bot entra como participante silencioso e grava.

Após o término, a transcrição fica disponível no dashboard.

Você pode exportar o texto com marcação de falas.

Opção 3: Whisper (OpenAI)

Vantagens: Alta precisão, funciona offline, gratuito e seguro. Ideal para quem quer privacidade.

Passo a passo:

Instale o Whisper:

Requer Python e Git.

Siga o tutorial oficial:

No terminal, execute:

 whisper arquivo.mp3 --language pt --model medium

O sistema gerará automaticamente arquivos .txt, .srt, .vtt com a transcrição.

Atenção: Por padrão, Whisper não separa falantes. Para isso, use o WhisperX:

🚀 Sugestão Final de Procedimento

Use Otter.ai ou Fireflies.ai como solução principal (fácil, integrada, com speaker ID).

Use Whisper se quiser total controle e privacidade local.

Sempre que possível, grave com áudio separado por participante (Zoom) ou use plugins com identificação de falas (Meet).

Com isso, você garante transcrições completas, com falas e ações interpretativas registradas, prontas para uso na reconstrução narrativa.

