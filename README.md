# BioPipeline: Plataforma Integrada para Análise Genômica e Proteica 🧬

[![Status: TCC](https://img.shields.io/badge/Status-TCC_em_Desenvolvimento-blue)](#)
[![Python Version](https://img.shields.io/badge/Python-3.9+-success.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](#)

> **Resumo do Projeto:** Uma solução de software projetada para orquestrar fluxos de trabalho (pipelines) de bioinformática, unindo o rigor analítico das ferramentas de linha de comando com a acessibilidade de interfaces modernas. Este projeto é desenvolvido como Trabalho de Conclusão de Curso (TCC).

---

## 🔬 Motivação e Justificativa

A bioinformática moderna depende de uma vasta gama de softwares especializados (frequentemente desenvolvidos em linguagens distintas como C++, Perl, R e Python). O grande desafio técnico e científico atual é que muitos pesquisadores, biólogos e profissionais da saúde possuem dados valiosos, mas enfrentam barreiras operacionais devido à falta de conhecimento em programação e administração de sistemas.

O **BioPipeline** nasce com um forte valor científico: democratizar a montagem e análise de genomas. Ao abstrair a complexidade de configuração, gerenciamento de dependências e passagem de parâmetros via terminal, o software permite que o pesquisador foque exclusivamente na interpretação biológica e no avanço da ciência.

## 🎯 Objetivos

### Objetivo Geral
Desenvolver e implementar uma plataforma de software capaz de integrar múltiplas ferramentas de bioinformática em um pipeline contínuo, automatizado e com persistência de dados.

### Objetivos Específicos
* **Acessibilidade:** Criar duas interfaces de uso — uma CLI (Command Line Interface) otimizada para servidores dedicados/HPC e uma interface Desktop (GUI) para usuários sem experiência em programação.
* **Orquestração de Dados (Big Data):** Implementar um sistema de banco de dados para salvar os resultados intermediários de cada etapa, permitindo que as ferramentas subsequentes consumam os dados automaticamente.
* **Parsing Customizado:** Desenvolver uma biblioteca nativa otimizada para leitura, identificação e validação de arquivos genômicos padrão (`.fasta` e `.gbk`).
* **Automação de Aquisição:** Implementar rotinas para captura automatizada de genomas em bancos de dados públicos (como o NCBI) a partir de tabelas TSV/CSV.

---

## 🛠️ Arquitetura e Tecnologias

Para suportar o alto volume de processamento exigido por análises genômicas, a arquitetura foi desenhada com foco em escalabilidade e processamento assíncrono:

* **Linguagem Principal:** Python (orquestração de processos e backend).
* **Processamento e Mensageria:** Implementação de filas de mensagens (RabbitMQ/Redis) para gerenciar rotinas de longa duração e processamento de Big Data em background.
* **Banco de Dados:** Banco de dados relacional para armazenamento de metadados, parâmetros de execução e rastreabilidade dos experimentos.
* **Ferramentas Integradas (Wrappers):** O software atua como um motor que encapsula e executa softwares de terceiros.

---

## 🧬 Pipeline de Análise (Escopo Funcional)

O sistema automatiza o seguinte fluxo de trabalho científico:

### 1. Aquisição e Qualidade
* **Genome_Picker:** Módulo de download em lote (NCBI).
* **FastQC e FastP:** Controle de qualidade, filtragem e trimming de leituras (reads).

### 2. Montagem e Filogenia
* **Unicycler:** Algoritmo de montagem de genomas bacterianos.
* **Quast:** Avaliação de métricas de qualidade da montagem.
* **IQ-TREE e OrthoFinder:** Inferência filogenética e análise de ortologia.

### 3. Pós-Montagem e Proteômica
* **Prokka e Bakta:** Anotação rápida e padronização de genomas.
* **Panvita 2 e Abricate:** Análise de pangenoma, busca por fatores de virulência e resistência antimicrobiana (AMR).
* **BRIGS e Circos:** Geração de mapas genômicos circulares.
* **Kódon-X:** Análise avançada e estudo de proteínas.

---

## 👥 Equipe e Orientação

Este projeto é desenvolvido como requisito para a obtenção do grau de Bacharel em [Nome do Seu Curso] pela [Nome da Sua Universidade/Instituição].

* **[David / David Dias Pinto]** - *Desenvolvedor* - [LinkedIn](#) | [GitHub](#github.com/damazu)
* **[Vinicius / Vinicius Salles de Oliveira]** - *Desenvolvedor* - [LinkedIn](#) | [GitHub](#)
* **Victor / [Victor Silveira Caricatte De Araújo ]** - *Cliente* - [LinkedIn](#) | [GitHub](#)
* **[Leonardo Vilela Cardoso]** - *Professor(a) Orientador(a)* - [Lattes](#)
* **[João Pedro Oliveira Batisteli]** - *Coorientador(a)* - [Lattes](#)

---

## 🏛️ Apoio Institucional

*(Opcional: Se vocês usaram os computadores de algum laboratório específico ou tiveram bolsa, mencione aqui. Ex: Agradecimento ao Laboratório de Bioinformática da Universidade X pelo suporte computacional).*