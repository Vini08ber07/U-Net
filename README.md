# U-Net

## Breve descrição do projeto

  A arquitetura conhecida como U-Net (proposta em 2015 no artigo "U-Net: Convolutional Networks for Biomedical Image Segmentation") já é amplamente conhecida no cenário de segmentação de imagens. No presente projeto ela foi implementada visando especificamente segmentar imagens de ressonâncias magnéticas para encontrar LGGs (gliomas de baixo grau).
  A motivação para criação deste código surgiu a partir de um projeto de feira de ciências escolar, em que buscamos apresentar uma proposta de implementação em larga escala da arquitetura no SUS, por conta do grande potencial de ganho econômico, ganho de eficiência e ganho de vidas.

## O que foi utilizado para cria-lá, treina-lá e como o código foi organizado?
  
  O código foi criado se baseando no PyTorch. Para treinamento e inferência nos utilizamos da GPU do Google Colab integrada ao VS Code, porém nada te impede de utilizar a sua própria GPU, apenas algumas poucas mudanças serão necessárias (retirada dos imports do Google e mudanças de caminhos).

  O dataset utilizado para treino e inferência foi o "Brain MRI Segmentation" postado por Matheusz Buda no Kaggle. Ele contém 3929 imagens de ressonâncias magnéticas de mais de 110 pacientes diferentes; cada imagem possui uma label com a posição do LGG.
        
  O código foi divido nas seguintes principais células no notebook: uma primeira parte de imports de librarys; uma segunda parte para setar corretamente o dataset; uma terceira que cria realmente a arquitetura; uma quarta que seta a função de treino (função de loss utilizada foi uma combinação da F.cross_entropy com a dice_loss); uma quinta que seta a função de avaliação (métricas utilizadas: dice score e IoU); e por fim um célula para plotar as imagens segmentadas.
