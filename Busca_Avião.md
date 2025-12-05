># Trabalho de PM 
**✈️ Trajeto do Avião para determinados Pontos**

O algoritmo se baseia na busca em largura **(BFS)**, onde o avião possui um trajeto entre pontos e a busca em largura percorre cada ponto para saber qual a tragetória mais rápida e ideal paté determinado ponto.           

---      
# Adicionar codigo aqui ⬇️

### Algoritmo
``` python
grafo = {
    "A": ["B", "C"],
    "B": ["D"],
    "C": ["D", "B"],
    "D": []
}

# Função BFS para encontrar um caminho de A até B
def bfs_caminho(grafo, inicio, destino):
    fila = [[inicio]]      # começamos com o caminho inicial
    visitados = set()      # para não visitar o mesmo ponto duas vezes

    while fila:
        caminho = fila.pop(0)   # pega o próximo caminho da fila
        atual = caminho[-1]     # último ponto do caminho

        if atual == destino:
            return caminho      # encontramos o destino

        if atual not in visitados:
            visitados.add(atual)
            for vizinho in grafo[atual]:
                novo_caminho = caminho + [vizinho]  # adiciona vizinho ao caminho
                fila.append(novo_caminho)

    return None  # caminho não encontrado

# Testando a função
caminho = bfs_caminho(grafo, "A", "B")
print("Caminho de A até B:", caminho)
```
### Execução
``` python
# Execução
Caminho de A até D: ['A', 'B', 'D']
```
Na execução mostra o caminho do ponto A até o D, mostrando o percurso até o destino.
