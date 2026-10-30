# Pipeline Analítico: Evolução dos Preços de Varejo de Memórias (DRAM e NAND) no Contexto da IA Generativa

Repositório aberto com os scripts analíticos e a base de dados processada do Trabalho de Conclusão de Curso (TCC) na modalidade de Artigo Científico:

> **ANÁLISE EXPLORATÓRIA DA EVOLUÇÃO DOS PREÇOS DE VAREJO DE MEMÓRIAS (DRAM E NAND FLASH) NO CONTEXTO DA EXPANSÃO DA INTELIGÊNCIA ARTIFICIAL GENERATIVA**  
> **Autor:** Vitor de Souza Vieira  
> **Orientador:** Prof. Welquer Kestering Esser  
> **Instituição:** Centro Universitário Barriga Verde (UNIBAVE) — Sistemas de Informação

---

## 1. Visão Geral e Reprodutibilidade

Este repositório contém o código e os dados necessários para reproduzir integralmente as análises descritivas, testes de quebra estrutural e visualizações apresentadas no artigo.

- **Linguagem:** Python 3.12+
- **Semente Aleatória:** seed = 42 (para reprodutibilidade estocástica nos testes de bootstrap)
- **Deflação Monetária:** Preços expressos em US$ constantes de setembro de 2026 via índice CPIAUCSL (*FRED*)

---

## 2. Estrutura do Repositório

`	ext
├── data/
│   ├── memory-prices.csv                       # Dados brutos consolidados do Stanford DAM Project
│   ├── cpiaucsl.csv                            # Série histórica do índice inflacionário CPIAUCSL (FRED)
│   └── processed/
│       └── memory_prices_clean_2019_2026.csv   # Base tratada, deflacionada e reindexada (jan/2019 a set/2026)
├── tcc.ipynb                                   # Caderno Jupyter principal com o pipeline analítico completo
├── requirements.txt                            # Versões exatas dos pacotes Python utilizados
├── .gitignore                                  # Arquivos ignorados pelo controle de versão
└── README.md                                   # Documentação e instruções de execução
`

---

## 3. Instruções de Instalação e Execução

### Passo 1: Clonar o Repositório
`ash
git clone https://github.com/vitorszvr/tcc-analise.git
cd tcc-analise
`

### Passo 2: Criar e Ativar Ambiente Virtual (Recomendado)
- **Windows (PowerShell):**
  `powershell
  python -m venv .venv
  .\.venv\Scripts\Activate.ps1
  `
- **Linux / macOS (Bash):**
  `ash
  python3 -m venv .venv
  source .venv/bin/activate
  `

### Passo 3: Instalar as Dependências
`ash
pip install --upgrade pip
pip install -r requirements.txt
`

### Passo 4: Executar o Caderno Analítico
`ash
jupyter notebook tcc.ipynb
`
Execute as células sequencialmente (Kernel -> Restart & Run All) para gerar todas as tabelas estatísticas, cálculos de volatilidade e modelos de ponto de mudança (*Hinge Regression* e *Step Change* de Bai-Perron).

---

## 4. Fontes Primárias dos Dados

1. **Stanford Differentiated Access Memories (DAM) Project:**
   - Séries históricas de John C. McCallum (1956–jul/2024);
   - Monitoramento contemporâneo de mercado via Keepa / Amazon EUA (ago/2024–set/2026);
   - Estimativas de dispêndio com HBM modeladas pela Epoch AI e relatórios setoriais da TrendForce e SemiAnalysis.
2. **Federal Reserve Bank of St. Louis (FRED):**
   - Série CPIAUCSL (*Consumer Price Index for All Urban Consumers: All Items in U.S. City Average*).

---

## 5. Licença

Este repositório é disponibilizado para fins acadêmicos e educacionais sob a licença [MIT](https://opensource.org/licenses/MIT).