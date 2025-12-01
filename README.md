# Automação da Geração de Lógica de Controle para Simuladores de Satélites utilizando Aprendizado de Máquina: Uma Abordagem Baseada em Árvores de Decisão

## Visão Geral do Projeto

Este projeto automatiza o processo de **extração de regras de negócio e a geração de código executável** diretamente de documentos de especificações técnicas no formato `.docx`. Ao invés de transcrever manualmente as tabelas de pré-condições e efeitos, que são comuns em documentações de engenharia de sistemas, este pipeline de Machine Learning aprende essas relações e as converte em código Python e C++.

O objetivo principal é **acelerar o desenvolvimento**, **reduzir erros humanos** e **garantir a consistência** entre a documentação e a implementação de sistemas complexos.

## 🌟 Funcionalidades

*   **Extração Inteligente de Tabelas**: Lê documentos `.docx` e identifica automaticamente tabelas que descrevem pré-condições e efeitos, filtrando apenas as relevantes.
*   **Conversão para Formato Tabular**: As tabelas extraídas são padronizadas e salvas em um arquivo `.xlsx`, com cada tabela em uma aba separada, para fácil visualização e verificação.
*   **Pré-processamento de Dados**: Unifica e limpa os dados, tratando valores ausentes e combinando múltiplos efeitos em uma única saída para o modelo de ML.
*   **Aprendizado de Máquina (Machine Learning)**:
    *   Utiliza um modelo de **Árvore de Decisão** para aprender as regras lógicas intrínsecas às tabelas de pré-condições e efeitos.
    *   Inclui um modelo de **Random Forest** para comparação e avaliação da acurácia.
*   **Geração de Código Automatizada**:
    *   Gera um arquivo Python (`.py`) contendo uma função com lógica `if/else` que replica as regras aprendidas pela Árvore de Decisão.
    *   Gera um arquivo C++ (`.cpp`) equivalente, otimizado para integração em ambientes de alta performance ou sistemas embarcados.
*   **Download Automático**: Os arquivos Excel e os códigos gerados são automaticamente baixados para o usuário.

## 🛠️ Tecnologias Utilizadas

*   **Python 3.x**
*   **Bibliotecas Python**:
    *   `pandas`: Manipulação e análise de dados.
    *   `scikit-learn`: Implementação de modelos de Machine Learning (Decision Tree, Random Forest, OneHotEncoder, LabelEncoder).
    *   `python-docx`: Leitura e extração de conteúdo de arquivos `.docx`.
    *   `openpyxl`: Manipulação de arquivos `.xlsx`.
    *   `matplotlib`: Visualização de dados (e.g., matriz de confusão).
    *   `numpy`: Operações numéricas.

## 🚀 Como Usar

Este projeto foi desenvolvido para ser executado em um ambiente Google Colab, que já oferece muitas das dependências necessárias.

### 1. Clonar o Repositório (Opcional, se você estiver usando o notebook diretamente no Colab)

```bash
git clone <URL_DO_SEU_REPOSITÓRIO>
cd <NOME_DO_REPOSITÓRIO>
```

### 2. Abrir no Google Colab

Faça o upload do arquivo `.ipynb` para o Google Colab ou abra-o diretamente se já estiver integrado ao GitHub.

### 3. Executar as Células

Siga a ordem de execução das células no notebook:

1.  **Instalação de Bibliotecas**: A primeira célula instalará `python-docx` e `openpyxl`.
2.  **Upload de Arquivos `.docx`**: Você será solicitado a fazer o upload dos seus documentos Word que contêm as tabelas de pré-condições e efeitos. Certifique-se de que os nomes das colunas de pré-condições e efeitos sigam um padrão consistente.
3.  **Processamento DOCX para Excel**: Esta seção extrairá as tabelas relevantes e as salvará em um arquivo `.xlsx`, que será baixado automaticamente.
4.  **Desenvolvimento do Modelo de ML e Geração de Código Python**: Você será solicitado a fazer o upload do arquivo `.xlsx` gerado na etapa anterior. O notebook treinará o modelo de ML e gerará o código Python (`.py`), que será baixado automaticamente.
5.  **Geração de Código C++**: Semelhante à etapa anterior, mas gerará o código C++ (`.cpp`), também com download automático.

## 🎯 Saídas do Projeto

Ao final da execução, você terá os seguintes arquivos:

*   **`_tabelas.xlsx`**: Um arquivo Excel contendo todas as tabelas de pré-condições/efeitos extraídas dos seus documentos Word, cada uma em uma aba.
*   **`decidir_efeito_one_hot.py`**: Um arquivo Python com uma função `decidir_efeito_one_hot` que implementa a lógica aprendida pela Árvore de Decisão.
*   **`decidir_efeito_one_hot.cpp`**: Um arquivo C++ com uma função `decidir_efeito_one_hot` equivalente, para integração em projetos C++.

## 👥 Contribuição

Sinta-se à vontade para contribuir com este projeto! Sugestões, melhorias e relatórios de bugs são muito bem-vindos. Por favor, abra uma *issue* ou um *pull request*.

## 📄 Agradecimentos

Agradeço pela oportunidade do HBR e pelo apoio da minha orientadora Drª Simone Rocio e da Drª Ana Ambrosio pelas orientações para definir tema e identificar uma problemática na área.