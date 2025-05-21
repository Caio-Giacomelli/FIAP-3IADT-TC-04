# FIAP-3IADT-TC-04

## Como utilizar este código

A implementação foi realizada em Notebook, através do Google Collab. Para reproduzí-la, é necessário conectar ao seu google drive e possuir o vídeo salvo.

Altere a estrutura de pastas e o nome do vídeo conforme estrutura abaixo, localizada na seção "Manipulação dos vídeos e inicialização do processamento"

```python
  folder_path = '/content/drive/MyDrive/FIAP/Trabalho04'
  input_video_path = os.path.join(folder_path, 'video', 'Unlocking Facial Recognition_ Diverse Activities Analysis.mp4')
  output_video_path = os.path.join(folder_path, 'output', 'output_video.mp4')
```

## Resumo

Neste Tech Challenge, realizamos o desafio de implementar reconhecimento facial, análise de expressões emocionais, detecção de atividades em tempo real e geração de resumo destas atividades. Em conjunto, definimos uma anomalia e à detectamos em vídeo.


O reconhecimento facial foi realizado de duas formas. Utilizamos haarcascades como classificador da biblioteca de cv2 em conjunto com Deep Face para identificar o rosto e mapear as emoções associadas ao rosto detectado, já também solucionando o segundo desafio, de análise de expressões emocionais. O método detect_face_expressions é o responsável por esta lógica. Também utilizamos o MediaPipe para identificação de rosto, porém utilizamos seus landmarks para definir anomalias, escolhendo a distância entre o nariz e a boca superiores ou inferiores à um limiar, para ser identificada como anomalia.

A geração de resumo em tempo real foi realizada utilizando BlipProcessor e BlipForConditionalGeneration, da biblioteca de transformers.E para finalizar, resumimos as Captions e Emoções utilizando o Summarizer

**Total de Frames analisados:** 3326

**Total de Anomalias encontradas:** 35

**Tempo total de processamento:** 32 minutos

**Principais emoções encontradas:** Neutra, medo, felicidade, raiva, tristeza, surpresa
