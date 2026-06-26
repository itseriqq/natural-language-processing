# Análise de Sentimentos e Emoções em Respostas do X/Twitter com LangChain e Gemini

Projeto prático da disciplina **Processamento de Linguagem Natural [2025-Q3]** da UFABC, desenvolvido em notebook no Google Colab com uso do framework **LangChain**, do modelo **Gemini 2.5-Flash** e da API **TwitterAPI.io**.

## Visão geral

Este projeto investiga como diferentes grupos reagem a um mesmo acontecimento político por meio de respostas publicadas no X/Twitter. A proposta central foi analisar sentimentos, emoções, classificação textual e extração de palavras-chave em comentários associados a figuras influentes de espectros políticos distintos.

O estudo toma como ponto de partida respostas a tweets relacionados ao assassinato de Charlie Kirk, buscando observar padrões discursivos, polarização, tom emocional e diferenças de posicionamento entre públicos distintos.

## Objetivos

- Aplicar técnicas de **Processamento de Linguagem Natural** em dados reais coletados da web.
- Integrar **LangChain** com um **LLM** para automatizar análises textuais em escala.
- Comparar reações e enquadramentos discursivos em torno de um mesmo evento político.
- Explorar sinais de polarização por meio de sentimento, emoção e classe textual inferida a partir dos tweets.

## Técnicas de PLN utilizadas

- **Análise de sentimentos**
- **Detecção de emoções**
- **Classificação de textos**
- **Extração de palavras-chave**

Essas técnicas foram implementadas com apoio do Gemini via prompts estruturados, permitindo transformar respostas livres em categorias analíticas mais fáceis de comparar entre grupos.

## Tecnologias utilizadas

| Componente | Uso no projeto |
|---|---|
| **Google Colab** | Ambiente de execução do notebook |
| **LangChain** | Orquestração de prompts e integração com o LLM |
| **Gemini 2.5-Flash** | Modelo principal para classificação e análise textual |
| **TwitterAPI.io** | Coleta de dados do X/Twitter |
| **Python** | Manipulação, processamento e análise dos dados |
| **BeautifulSoup / requests** | Extração de conteúdo de página web usada na etapa de captura de contas |
| **Matplotlib / Counter** | Geração de visualizações e contagens agregadas |

## Fluxo do projeto

O notebook segue um pipeline prático de coleta, preparação e análise:

1. Definição do problema e do recorte analítico no contexto político.
2. Coleta de tweets e respostas por meio da **TwitterAPI.io**.
3. Extração complementar de contas populares a partir de uma página da web, usando raspagem de texto e o Gemini para inferir usernames prováveis.
4. Construção de prompts com **LangChain** para classificar sentimento e emoções dos tweets.
5. Processamento em lote das respostas coletadas.
6. Consolidação dos resultados e geração de gráficos com as categorias encontradas.

## Estrutura analítica

O projeto trabalha com listas de tweets de diferentes perfis e processa cada item com um prompt padronizado que retorna uma categoria de sentimento e uma lista de emoções. O conjunto de emoções considerado inclui classes como alegria, tristeza, raiva, ironia, medo, desprezo, esperança, confiança, decepção e outras, além de casos indefinidos.

Também há o uso de contagens agregadas e gráficos para comparar distribuições de categorias, o que permite observar tendências gerais de reação por perfil ou conjunto de respostas.

## Como executar

### 1. Pré-requisitos

- Conta Google para uso do **Google Colab**
- Chave de API do **Gemini**
- Acesso à **TwitterAPI.io**

### 2. Instalação de dependências

No Colab, instale a biblioteca principal de integração com Gemini:

```python
!pip install -qU langchain-google-genai
```

Esse comando aparece no notebook como parte da configuração inicial do ambiente.

### 3. Configuração da chave da API

O notebook utiliza variáveis de ambiente e integração com `userdata` no Colab para recuperar a chave do Gemini. Ajuste essa etapa conforme sua forma de armazenamento de credenciais.

### 4. Execução

- Abra o notebook no Google Colab.
- Configure as credenciais necessárias.
- Execute as células na ordem.
- Aguarde a coleta, o processamento e a geração das análises.

## Possíveis resultados esperados

Os resultados incluem classificação de tweets por polaridade, identificação de emoções dominantes, listas processadas por perfil e visualizações das distribuições de categorias. Isso permite comparar como comunidades diferentes reagem ao mesmo fato e quais tons emocionais aparecem com mais frequência em cada grupo.

## Aplicações

Este projeto pode ser adaptado para:

- monitoramento de debates políticos em redes sociais;
- análise de reputação;
- estudos de polarização discursiva;
- detecção de padrões emocionais em comunidades online;
- apoio a pesquisas acadêmicas em PLN e ciência de dados social.

## Equipe

- **Erick Augusto Silva Pereira** — RA: 11202130310
- **Victor Ravazio de Lima** — RA: 11201920941

## Observações

O notebook foi desenvolvido como entrega acadêmica e contém instruções do enunciado original da disciplina, além das células de implementação e visualização. Como o projeto está em formato `.ipynb`, este README serve como uma camada de apresentação para contextualizar rapidamente objetivo, stack e fluxo analítico antes da leitura detalhada do notebook.
