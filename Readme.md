Checkpoint 2 — Dynamic Programming: Memoização + Rotas de Metrô
Disciplina: FIAP — Dynamic Programming
Checkpoint: 2 (Recursão com Memoização)
 
📍 Grupo
Rafael Falaguasta Ferraz Rm56174
Victor Simoes Altieri Rm565288
Eduardo Antonio Delarissia Rm563468
 
🎯 Objetivo
Implementar um sistema de otimização de rotas para redes de metrô em três cidades (Beijing, San Francisco, São Paulo) usando recursão com memoização. O projeto encontra o caminho mais curto e mais longo entre duas estações, considerando fatores dinâmicos de horário (penalidades e bônus).
 
📂 Estrutura
checkpoint-2-dynamic-programming/
├── notebook.ipynb          ← Arquivo principal 
└── README.md              ← 
 
🚀 Como Usar
Google Colab (Recomendado)
Jupyter Local
bashpip install pandas folium
jupyter notebook notebook.ipynb
 
📊 Conteúdo do Notebook
Grafos Modelados
CidadeOrigemDestinoEstações🇨🇳 BeijingSihui EastXizhimen18🇺🇸 San FranciscoDublin/PleasantonDaly City23🇧🇷 São PauloTucuruviCapão Redondo21
Características
 
✅ Representação em dicionário de adjacência
✅ Múltiplos caminhos por cidade
✅ Coordenadas geográficas para visualização
 
 
⏰ Fatores de Horário
PeríodoHorárioFatorDescriçãoMadrugada5h-7h0.6xBônusPico Manhã7h-9h1.5xPenalidadeNormal9h-17h1.0xSem alteraçãoPico Tarde17h-20h2.0xPenalidade máximaNoite20h+0.8xBônus
 
🔧 Algoritmos Implementados
1. Caminho Mais Curto (Recursão + Memoização)
pythonclass CaminhoMaisCurto:
    def buscar(self, origem, destino, horario, visitados=frozenset()):
        # Caso base
        if origem == destino:
            return (0, [origem])
        
        # Verificar cache
        if em_cache:
            return cache[...]
        
        # Explorar vizinhos
        melhor_custo = infinito
        for vizinho in grafo[origem]:
            peso_ajustado = peso * fator_horario(horario)
            custo_futuro = buscar(vizinho, destino, horario)
            
            if custo_futuro < melhor_custo:
                melhor_custo = custo_futuro
        
        # Armazenar em cache
        cache[...] = (melhor_custo, caminho)
        return resultado
Complexidade: O(V² + E)
 
2. Caminho Mais Longo (Backtracking)
Explora todos os caminhos possíveis sem ciclos usando backtracking para encontrar a rota com mais estações.
Complexidade: O(V!) no pior caso
 
📈 Resultados
Beijing
 
Caminho curto: ~18 min (11 estações)
Caminho longo: ~42 min (15 estações)
Tempo execução: < 1ms
 
San Francisco
 
Caminho curto: ~29 min (14 estações)
Caminho longo: ~55 min (19 estações)
Tempo execução: < 1ms
 
São Paulo
 
Caminho curto: ~22 min (passa por Sé e Brooklin)
Caminho longo: ~49 min (18 estações)
Tempo execução: < 1ms
 
 
🗺️ Visualização
O notebook inclui 3 mapas Folium interativos mostrando:
 
🟢 Estação de origem
🔴 Estação de destino
🔵 Outras estações
🟠 Caminho mais curto (laranja)
🟣 Caminho mais longo (roxo tracejado)
 
 
📊 Análise de Performance
Com Memoização
 
Chamadas: ~100 por execução
Tempo: < 1ms
Memória: ~50KB
 
Sem Memoização (estimado)
 
Chamadas: ~300-500
Tempo: 5-10ms
Melhoria: ~70-80% mais rápido com cache
 
 
🔍 Complexidade Big-O
MétricaSem MemoizaçãoCom MemoizaçãoTempoO(V^E) — ExponencialO(V² + E) — PolinomialEspaçoO(V)O(V²)
Conclusão: Memoização converte problema exponencial em polinomial, tornando possível encontrar soluções ótimas rapidamente.
 
🛠️ Tecnologias
 
Python 3.9+
pandas — Análise de dados
folium — Mapas interativos
tracemalloc — Análise de memória
functools — Suporte a memoização
 
 
📋 Requisitos Atendidos
 
 Modelagem: 3 grafos com 15+ estações cada
 Múltiplos caminhos por grafo
 Recursão com memoização (cache manual)
 Caminho mais longo com backtracking
 Penalidades e bônus por horário (5 faixas)
 Análise de desempenho (tempo + memória)
 Visualização com Folium
 Notebook documentado com Markdown
 Repositório GitHub público
 
