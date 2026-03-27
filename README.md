# 🎙️ Assistente de Voz com IA para Entrevistas de Emprego

Um assistente virtual interativo desenvolvido em Python no Google Colab. Este projeto utiliza inteligência artificial para simular uma entrevista de emprego, conduzindo a conversa por voz de forma dinâmica e respondendo ao candidato em tempo real.

## 🎯 Objetivo do Projeto
Criar uma ferramenta funcional e acessível para treinar habilidades de comunicação em entrevistas. O sistema capta o áudio do usuário, transcreve para texto, gera uma resposta contextualizada agindo como um recrutador e, por fim, sintetiza essa resposta em áudio.

## 🛠️ Tecnologias Utilizadas
* **Linguagem:** Python
* **Ambiente:** Google Colab
* **Captura de Áudio:** JavaScript (Web API) e `pydub`
* **Reconhecimento de Fala (STT):** [Whisper (OpenAI)](https://github.com/openai/whisper) - Modelo `small` para transcrição rápida e precisa.
* **Inteligência Artificial (LLM):** [Google Gemini API](https://aistudio.google.com/) (`google-genai`) - Modelo `gemini-2.5-flash` para geração das respostas do recrutador.
* **Síntese de Voz (TTS):** `gTTS` (Google Text-to-Speech) para transformar a resposta da IA em áudio.

## 🚀 Como Executar o Projeto

Como o projeto foi construído para o Google Colab, não é necessário instalar dependências complexas na sua máquina local.

1. **Acesse o Notebook:** Abra o arquivo `.ipynb` deste repositório no Google Colab.
2. **Chave de API:** Você precisará de uma API Key gratuita do Gemini.
   * Acesse o [Google AI Studio](https://aistudio.google.com/) e gere a sua chave.
   * Cole a chave na variável `GOOGLE_API_KEY` dentro do código (Etapa 3).
3. **Execução:**
   * Rode as células sequencialmente.
   * Na primeira célula, conceda permissão ao navegador para usar o microfone.
   * Fale sua resposta para a pergunta da entrevista.
   * Aguarde o processamento (transcrição -> IA -> áudio) e ouça o retorno do recrutador!

## 🧩 Estrutura do Fluxo
1. **Gravação:** Um script embutido em JavaScript acessa o microfone via navegador no Colab e salva um arquivo `.wav`.
2. **Transcrição:** O modelo Whisper processa o áudio `.wav` e extrai o texto falado.
3. **Processamento Semântico:** O texto é enviado ao Gemini junto com um *prompt* de sistema que o instrui a agir como um recrutador conciso e amigável.
4. **Sintetização:** A resposta em texto gerada pelo Gemini é convertida em fala pelo gTTS e reproduzida automaticamente no Colab.

## 💡 Próximos Passos e Melhorias
* Parametrizar o prompt da IA para focar em vagas específicas (ex: Desenvolvedor Front-end, Analista de Dados).
* Adicionar suporte nativo para simular a entrevista em inglês, o que é um excelente exercício para treinar conversação e vocabulário técnico no idioma.
* Criar um loop de conversação contínua para que a entrevista tenha múltiplas perguntas e respostas sem precisar rodar as células novamente.
