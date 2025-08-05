# CGAN para geração de mapas padrão com base em imagens via Satelite

Este projeto utiliza uma **Rede Adversária Generativa Condicional (CGAN)** para **gerar mapas estilizados** (como mapas de ruas, topográficos ou padrão OpenStreetMap) **a partir de imagens de satélite**. O objetivo é explorar como modelos GAN podem aprender a converter dados visuais complexos em representações simplificadas e úteis para navegação, análise urbana e planejamento geográfico.

## 🌍 Motivação

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

- **Gerador (Generator)**: Recebe uma imagem de satélite + ruído e tenta gerar um mapa correspondente.
- **Discriminador (Discriminator)**: Tenta distinguir entre mapas reais e mapas gerados, aprendendo a identificar falsificações.

A entrada condicional é a imagem de satélite, que guia o processo de geração. O treinamento segue o paradigma GAN clássico, com aprendizado competitivo entre os dois módulos.

---

## 🗂️ Estrutura do Projeto

o Código foi desenvolvido com jupyter, o dataset esta disponivel no link abaixo:</br>
http://efrosgans.eecs.berkeley.edu/pix2pix/datasets/</br>
para o modelo gerador, utilizo o modelo U-net, e para o modelo discriminador, utilizo o patchGAN. ambos modelos apresentam resultados parecidos em suas respectivas funções.
para o treinamento e validação, utilizo 1096 imagens, cada imagem apresenta dois modelos de mapas, um modelo via satelite e ao lado o modelo padrão para comparação:
![modelo 1](image/2.png)
![modelo 2](image/3.png)
![modelo 3](image/7.png)
