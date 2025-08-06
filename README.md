# CGAN para geração de mapas padrão com base em imagens via Satelite

Este projeto utiliza uma **Rede Adversária Generativa Condicional (CGAN)** para **gerar mapas estilizados** (como mapas de ruas, topográficos ou padrão OpenStreetMap) **a partir de imagens de satélite**. O objetivo é explorar como modelos GAN podem aprender a converter dados visuais complexos em representações simplificadas e úteis para navegação, análise urbana e planejamento geográfico.

## Motivação

Mapas são fundamentais para nossa compreensão do espaço geográfico, mas sua criação exige muito trabalho manual ou acesso a bancos de dados estruturados. Com a crescente disponibilidade de **imagens de satélite de alta resolução**, surge a oportunidade de **automatizar a geração de mapas** com técnicas de **inteligência artificial**.

Este projeto propõe o uso de uma CGAN para aprender a relação entre imagens de satélite e seus respectivos mapas, permitindo a conversão automática com qualidade visual e semântica.

---

## Tecnologias utilizadas

- Python 3.10+
- TensorFlow / keras
- NumPy
- Matplotlib
- Ipython

---

## Arquitetura da CGAN

A CGAN é composta por dois módulos principais:

- **Gerador (Generator)**: para geração de imagens, foi escolhido o modelo U-net. esse modelo Recebe uma imagem de satélite + um ruído para gerar imagens, nesse caso, gerar imagens de mapas.
- **Discriminador (Discriminator)**: para classificação das imagens, foi escolhido o modelo patchGAN. esse modelo Tenta distinguir entre mapas reais e mapas gerados, aprendendo a identificar falsificações.

escolhi esses modelos para que não houvesse injustiças no treinamento. um modelo melhor que o outro poderia trazer resultados enviesados.

---

## Estrutura do Projeto

o Código foi desenvolvido com jupyter, o dataset esta disponivel no link abaixo:</br>
http://efrosgans.eecs.berkeley.edu/pix2pix/datasets/</br>
para o treinamento e validação, utilizo 1096 imagens, cada imagem apresenta dois modelos de mapas, um modelo via satelite e ao lado o modelo padrão para comparação:
![modelo 1](image/2.jpg)
![modelo 2](image/3.ipg)
![modelo 3](image/7.jpg)
o mapa via satelite é utilizado pela U-Net para o treinamento da geração da imagem, ja o mapa padrão e utilizado pelo patchGAN para a validação das imagens geradas.
para diverfisifcar o treinamento do modelo gerador, utilizo um dimensionamento aleatorio para que as imagens não apresentem padrões que possam atrapalhar no treinamento.</br>


---
## Resultado do Projeto
o treinamento foi composto por 40000 etapas. abaixo estao imagens do mapa via satelite, ao lado o mapa padrão real e por ultimo o mapa gerado pela IA:
![modelo 1](image/resultado_pix2pix_etapa_37000.png)
![modelo 2](image/resultado_pix2pix_etapa_38000.png)
![modelo 3](image/resultado_pix2pix_etapa_39000.png)

como nas imagens, o resultado ainda não foi tão preciso, alguns paramentros deverão ser modificados e tambem será muito bom aumentar o numero de epocas para que os resultados sejam ainda mais precisos.
esse projeto demonstra que a aplicação de IAs podem ser muito úteis para mapeamentos. os dois modelos de IA utilizados nesse projeto, são considerado modelos simples, porem, ainda assim conseguiram resultados sastifatorios.

