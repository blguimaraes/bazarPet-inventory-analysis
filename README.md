# BazarPet JF - Sistema de Análise de Inventário
Este projeto visa analisar os dados do inventário de itens e doações do BazarPet JF, gerando gráficos que facilitam o entendimento de tendências de doação, performance de doadores, itens mais doados, entre outras métricas relevantes.

## Estrutura do Projeto
A estrutura do projeto está organizada da seguinte forma:

``` Estrutura
resources/
│   ├── img/              # Pasta onde os gráficos gerados são salvos
│   └── inventory.db      # Banco de dados SQLite de exemplo, com as tabelas Donor e InventoryItem
utils/
│   ├── donationTendency.py    # Função que gera o gráfico de tendências de doação
│   ├── donorPerformance.py    # Função que gera o gráfico de performance dos doadores
│   ├── itemsByType.py         # Função que gera o gráfico de itens por tipo
│   ├── itemsTypeByDonor.py    # Função que gera o gráfico de tipo de itens por doador
│   └── missingItems.py        # Função que gera o gráfico de itens em falta
inventoryAnalysis.py           # Programa principal que roda todas as funções de análise
```

## Pré-requisitos
- Python 3.7 ou superior
- Biblioteca matplotlib para geração dos gráficos
- Biblioteca pandas para manipulação de dados
- SQLite3 (para manipulação do banco de dados SQLite)

## Instalação das Dependências
Use o pip para instalar as dependências necessárias:

```bash
pip install matplotlib pandas sqlite3
```

## Como usar o projeto
### 1. Preparação do Banco de Dados
O projeto já vem com um banco de dados SQLite de exemplo (inventory.db) contendo as tabelas Donor e InventoryItem. Caso deseje inserir novos dados ou modificar a estrutura, você pode usar ferramentas como DB Browser for SQLite ou acessar diretamente via Python.

### 2. Executando as Análises
Para gerar os gráficos, basta rodar o programa principal inventoryAnalysis.py. Ele executará todas as análises, salvará os gráficos na pasta `resources/img/` e apresentará os gráficos na tela automaticamente.

```bash
python inventoryAnalysis.py
```

Os gráficos gerados são:

- **Tendência de Doações** (`donationTendency.svg`): Exibe as variações nas doações ao longo do tempo.
- **Performance dos Doadores** (`donorPerformance.svg`): Mostra os doadores com mais contribuições.
- **Itens por Tipo** (`itemsByType.svg`): Representa o número de itens no inventário, categorizados por tipo.
- **Tipo de Itens por Doador** (`itemsTypeByDonor.svg`): Gráfico agrupado que exibe quais tipos de itens foram doados por cada doador.
- **Itens em Falta** (`missingItems.svg`): Mostra os itens que estão com estoque baixo ou em falta.
  
### 3. Adicionando Novas Análises
Se você deseja adicionar novas análises, basta criar um novo arquivo Python na pasta `utils/`, seguindo o padrão das funções já existentes. Depois, adicione a chamada dessa nova função no `inventoryAnalysis.p`y.

### Exemplo de Gráficos
Os gráficos gerados estarão disponíveis na pasta `resources/img/`.
