# AT4---SSD
# 🛡️ MVP — Detecção de Anomalias em Segurança Cibernética

## 📌 Sobre o projeto

Este projeto apresenta um **Mínimo Produto Viável (MVP)** para detecção de comportamentos anômalos em dados relacionados à segurança cibernética.

A solução utiliza técnicas de **aprendizado de máquina não supervisionado** para identificar registros que apresentam comportamentos diferentes do padrão observado nos dados.

O projeto foi desenvolvido em **Python**, com execução prevista no **Google Colab**, e utiliza o algoritmo **Isolation Forest** para identificar possíveis anomalias.

---

## 🎯 Objetivo

Desenvolver uma aplicação capaz de:

* analisar registros de acessos;
* identificar padrões de comportamento;
* detectar possíveis comportamentos anômalos;
* calcular um indicador de anomalia;
* classificar os registros identificados;
* apresentar os resultados por meio de gráficos e tabelas;
* gerar uma base de resultados para análise posterior.

> **Observação:** o MVP possui finalidade acadêmica e experimental. Os dados utilizados podem ser simulados e não representam necessariamente eventos reais de segurança.

---

## 🧩 Problema

Ambientes digitais podem gerar grandes quantidades de registros de acesso, tornando difícil identificar manualmente comportamentos fora do padrão.

Entre os comportamentos que podem ser analisados estão:

* quantidade elevada de tentativas de login;
* aumento de falhas de autenticação;
* acessos em horários incomuns;
* volume elevado de dados transferidos;
* utilização de múltiplas portas;
* acessos provenientes de endereços IP externos;
* combinações incomuns de diferentes características de acesso.

O MVP busca utilizar essas informações para auxiliar na identificação automática de registros potencialmente anômalos.

---

## 🔬 Metodologia

O processo de análise é dividido nas seguintes etapas:

```text
Dados de acesso
       ↓
Pré-processamento
       ↓
Análise exploratória
       ↓
Seleção das variáveis
       ↓
Isolation Forest
       ↓
Detecção de anomalias
       ↓
Cálculo do indicador
       ↓
Classificação
       ↓
Visualização dos resultados
```

---

## 🤖 Modelo utilizado

### Isolation Forest

O **Isolation Forest** é um algoritmo de aprendizado de máquina utilizado para detecção de anomalias.

A lógica do modelo consiste em identificar observações que podem ser isoladas mais facilmente do restante dos dados.

Neste projeto, o algoritmo analisa características dos registros de acesso e atribui uma indicação de comportamento normal ou anômalo.

A implementação utiliza a biblioteca `scikit-learn`.

---

## 📊 Variáveis analisadas

O conjunto de dados utilizado no MVP pode conter as seguintes variáveis:

| Variável           | Descrição                                  |
| ------------------ | ------------------------------------------ |
| `timestamp`        | Data e horário do acesso                   |
| `ip_address`       | Endereço IP associado ao acesso            |
| `login_attempts`   | Número de tentativas de login              |
| `session_duration` | Duração da sessão                          |
| `bytes_sent`       | Quantidade de dados enviados               |
| `bytes_received`   | Quantidade de dados recebidos              |
| `failed_logins`    | Número de tentativas de login malsucedidas |
| `unique_ports`     | Quantidade de portas diferentes utilizadas |
| `access_hour`      | Horário do acesso                          |
| `is_external_ip`   | Indicador de acesso externo                |

---

## 📈 Indicador de anomalia

Após a aplicação do modelo, os registros podem ser classificados em:

| Resultado  | Interpretação                                        |
| ---------- | ---------------------------------------------------- |
| `Normal`   | Comportamento próximo ao padrão observado            |
| `Anomalia` | Comportamento significativamente diferente do padrão |

O resultado deve ser interpretado como **um indicador para investigação**, e não como confirmação de um incidente de segurança.

---

## 🛠️ Tecnologias utilizadas

* **Python**
* **Google Colab**
* **Pandas**
* **NumPy**
* **Scikit-learn**
* **Matplotlib**
* **Seaborn**

---

## 📁 Estrutura do projeto

```text
mvp-deteccao-anomalias/
│
├── MVP_Deteccao_Anomalias.ipynb
│
├── data/
│   └── acessos_ciberneticos.csv
│
├── results/
│   └── resultados_anomalias.csv
│
├── README.md
│
└── requirements.txt
```

### Descrição dos arquivos

**`MVP_Deteccao_Anomalias.ipynb`**

Notebook principal contendo todo o processo de análise e detecção de anomalias.

**`data/`**

Diretório destinado aos dados utilizados pelo modelo.

**`results/`**

Diretório destinado aos resultados gerados pelo notebook.

**`requirements.txt`**

Lista das bibliotecas necessárias para execução do projeto.

---

## ▶️ Como executar

### 1. Clonar o repositório

```bash
git clone https://github.com/SEU-USUARIO/mvp-deteccao-anomalias.git
```

### 2. Acessar o diretório

```bash
cd mvp-deteccao-anomalias
```

### 3. Instalar as dependências

```bash
pip install -r requirements.txt
```

### 4. Executar o notebook

O notebook pode ser executado diretamente pelo **Google Colab**.

Outra opção é abrir localmente utilizando:

```bash
jupyter notebook
```

---

## ☁️ Execução no Google Colab

O projeto foi desenvolvido para facilitar a execução no Google Colab.

Após abrir o arquivo:

```text
MVP_Deteccao_Anomalias.ipynb
```

basta executar as células sequencialmente ou utilizar:

**Ambiente de execução → Executar tudo**

O notebook realizará o processamento dos dados e apresentará os resultados automaticamente.

---

## 📊 Resultados esperados

Ao final da execução, o MVP deverá apresentar:

* quantidade total de registros analisados;
* quantidade de registros classificados como anômalos;
* percentual de anomalias;
* distribuição dos registros;
* gráficos de comportamento;
* identificação dos registros potencialmente anômalos;
* arquivo com os resultados da análise.

Exemplo de saída:

```text
Total de registros: 1000
Registros normais: 940
Anomalias identificadas: 60
Percentual de anomalias: 6,0%
```

Os valores acima são apenas ilustrativos.

---

## ⚠️ Limitações do MVP

Por se tratar de uma primeira versão, o projeto apresenta algumas limitações:

* os dados podem ser simulados;
* o modelo não confirma a ocorrência de um ataque;
* não substitui ferramentas profissionais de segurança;
* a qualidade dos resultados depende das características dos dados;
* o modelo pode gerar falsos positivos e falsos negativos;
* os parâmetros do algoritmo podem precisar de ajustes para diferentes ambientes.

---

## 🚀 Possíveis melhorias

Como evolução do MVP, podem ser implementadas:

* integração com dados reais de logs;
* integração com sistemas SIEM;
* monitoramento em tempo real;
* criação de alertas automáticos;
* dashboard interativo;
* identificação de padrões por usuário;
* análise de endereços IP;
* integração com APIs de inteligência de ameaças;
* comparação entre diferentes algoritmos de detecção;
* armazenamento histórico dos eventos;
* criação de níveis de criticidade.

---

## 🔐 Segurança e privacidade

Para fins de demonstração, recomenda-se utilizar **dados fictícios ou anonimizados**.

Informações sensíveis, como endereços IP reais, credenciais, tokens, identificadores pessoais ou dados internos de empresas, não devem ser disponibilizadas publicamente no repositório.

---

## 📚 Referências

O projeto utiliza principalmente as seguintes tecnologias e conceitos:

* Python para desenvolvimento da aplicação;
* Pandas e NumPy para manipulação dos dados;
* Scikit-learn para implementação do modelo de aprendizado de máquina;
* Matplotlib e Seaborn para visualização dos resultados;
* Isolation Forest para detecção de anomalias.

---

## 👩‍💻 Projeto

**MVP de Detecção de Anomalias em Segurança Cibernética**

Projeto desenvolvido para fins de estudo, prototipagem e demonstração da aplicação de técnicas de análise de dados e aprendizado de máquina na área de segurança cibernética.

