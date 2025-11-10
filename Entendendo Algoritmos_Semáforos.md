># Atividade-de-PM
> nomes:  - ADS
---
- Atividade sobre o livro entendendo algoritmos. Criar um algoritmo melhorado do livro.
## Algoritmo Semáforo

```python
def semaforo_com_bfs_unificado(ciclos):
    estados = [
        ("Rua A: VERDE     | Rua B: VERMELHO", 15),
        ("Rua A: AMARELO   | Rua B: VERMELHO", 5),
        ("Rua A: VERMELHO  | Rua B: VERDE", 15),
        ("Rua A: VERMELHO  | Rua B: AMARELO", 5)
    ]
    for ciclo in range(1, ciclos + 1):
        print(f"Ciclo {ciclo}")
        for estado, duracao in estados:
            for t in range(1, duracao + 1):
                print(f"{estado} | Tempo: {t}")
                # Aqui nós também tratamos como “visita” para a BFS:
                print(f"(BFS) Visitando: {estado} | Tempo no estado: {t}")
        print("-" * 40)

# Executando
semaforo_com_bfs_unificado(1)
```
---
## Teste de Mesa
```python
Ciclo Semáforo

Rua A: VERDE     | Rua B: VERMELHO | Tempo: 1
(BFS) Visitando: Rua A: VERDE     | Rua B: VERMELHO | Tempo no estado: 1
Rua A: VERDE     | Rua B: VERMELHO | Tempo: 2
(BFS) Visitando: Rua A: VERDE     | Rua B: VERMELHO | Tempo no estado: 2
Rua A: VERDE     | Rua B: VERMELHO | Tempo: 3
(BFS) Visitando: Rua A: VERDE     | Rua B: VERMELHO | Tempo no estado: 3
Rua A: VERDE     | Rua B: VERMELHO | Tempo: 4
(BFS) Visitando: Rua A: VERDE     | Rua B: VERMELHO | Tempo no estado: 4
Rua A: VERDE     | Rua B: VERMELHO | Tempo: 5
(BFS) Visitando: Rua A: VERDE     | Rua B: VERMELHO | Tempo no estado: 5
Rua A: VERDE     | Rua B: VERMELHO | Tempo: 6
(BFS) Visitando: Rua A: VERDE     | Rua B: VERMELHO | Tempo no estado: 6
Rua A: VERDE     | Rua B: VERMELHO | Tempo: 7
(BFS) Visitando: Rua A: VERDE     | Rua B: VERMELHO | Tempo no estado: 7
Rua A: VERDE     | Rua B: VERMELHO | Tempo: 8
(BFS) Visitando: Rua A: VERDE     | Rua B: VERMELHO | Tempo no estado: 8
Rua A: VERDE     | Rua B: VERMELHO | Tempo: 9
(BFS) Visitando: Rua A: VERDE     | Rua B: VERMELHO | Tempo no estado: 9
Rua A: VERDE     | Rua B: VERMELHO | Tempo: 10
(BFS) Visitando: Rua A: VERDE     | Rua B: VERMELHO | Tempo no estado: 10
Rua A: VERDE     | Rua B: VERMELHO | Tempo: 11
(BFS) Visitando: Rua A: VERDE     | Rua B: VERMELHO | Tempo no estado: 11
Rua A: VERDE     | Rua B: VERMELHO | Tempo: 12
(BFS) Visitando: Rua A: VERDE     | Rua B: VERMELHO | Tempo no estado: 12
Rua A: VERDE     | Rua B: VERMELHO | Tempo: 13
(BFS) Visitando: Rua A: VERDE     | Rua B: VERMELHO | Tempo no estado: 13
Rua A: VERDE     | Rua B: VERMELHO | Tempo: 14
(BFS) Visitando: Rua A: VERDE     | Rua B: VERMELHO | Tempo no estado: 14
Rua A: VERDE     | Rua B: VERMELHO | Tempo: 15
(BFS) Visitando: Rua A: VERDE     | Rua B: VERMELHO | Tempo no estado: 15
Rua A: AMARELO   | Rua B: VERMELHO | Tempo: 1
(BFS) Visitando: Rua A: AMARELO   | Rua B: VERMELHO | Tempo no estado: 1
Rua A: AMARELO   | Rua B: VERMELHO | Tempo: 2
(BFS) Visitando: Rua A: AMARELO   | Rua B: VERMELHO | Tempo no estado: 2
Rua A: AMARELO   | Rua B: VERMELHO | Tempo: 3
(BFS) Visitando: Rua A: AMARELO   | Rua B: VERMELHO | Tempo no estado: 3
Rua A: AMARELO   | Rua B: VERMELHO | Tempo: 4
(BFS) Visitando: Rua A: AMARELO   | Rua B: VERMELHO | Tempo no estado: 4
Rua A: AMARELO   | Rua B: VERMELHO | Tempo: 5
(BFS) Visitando: Rua A: AMARELO   | Rua B: VERMELHO | Tempo no estado: 5
Rua A: VERMELHO  | Rua B: VERDE | Tempo: 1
(BFS) Visitando: Rua A: VERMELHO  | Rua B: VERDE | Tempo no estado: 1
Rua A: VERMELHO  | Rua B: VERDE | Tempo: 2
(BFS) Visitando: Rua A: VERMELHO  | Rua B: VERDE | Tempo no estado: 2
Rua A: VERMELHO  | Rua B: VERDE | Tempo: 3
(BFS) Visitando: Rua A: VERMELHO  | Rua B: VERDE | Tempo no estado: 3
Rua A: VERMELHO  | Rua B: VERDE | Tempo: 4
(BFS) Visitando: Rua A: VERMELHO  | Rua B: VERDE | Tempo no estado: 4
Rua A: VERMELHO  | Rua B: VERDE | Tempo: 5
(BFS) Visitando: Rua A: VERMELHO  | Rua B: VERDE | Tempo no estado: 5
Rua A: VERMELHO  | Rua B: VERDE | Tempo: 6
(BFS) Visitando: Rua A: VERMELHO  | Rua B: VERDE | Tempo no estado: 6
Rua A: VERMELHO  | Rua B: VERDE | Tempo: 7
(BFS) Visitando: Rua A: VERMELHO  | Rua B: VERDE | Tempo no estado: 7
Rua A: VERMELHO  | Rua B: VERDE | Tempo: 8
(BFS) Visitando: Rua A: VERMELHO  | Rua B: VERDE | Tempo no estado: 8
Rua A: VERMELHO  | Rua B: VERDE | Tempo: 9
(BFS) Visitando: Rua A: VERMELHO  | Rua B: VERDE | Tempo no estado: 9
Rua A: VERMELHO  | Rua B: VERDE | Tempo: 10
(BFS) Visitando: Rua A: VERMELHO  | Rua B: VERDE | Tempo no estado: 10
Rua A: VERMELHO  | Rua B: VERDE | Tempo: 11
(BFS) Visitando: Rua A: VERMELHO  | Rua B: VERDE | Tempo no estado: 11
Rua A: VERMELHO  | Rua B: VERDE | Tempo: 12
(BFS) Visitando: Rua A: VERMELHO  | Rua B: VERDE | Tempo no estado: 12
Rua A: VERMELHO  | Rua B: VERDE | Tempo: 13
(BFS) Visitando: Rua A: VERMELHO  | Rua B: VERDE | Tempo no estado: 13
Rua A: VERMELHO  | Rua B: VERDE | Tempo: 14
(BFS) Visitando: Rua A: VERMELHO  | Rua B: VERDE | Tempo no estado: 14
Rua A: VERMELHO  | Rua B: VERDE | Tempo: 15
(BFS) Visitando: Rua A: VERMELHO  | Rua B: VERDE | Tempo no estado: 15
Rua A: VERMELHO  | Rua B: AMARELO | Tempo: 1
(BFS) Visitando: Rua A: VERMELHO  | Rua B: AMARELO | Tempo no estado: 1
Rua A: VERMELHO  | Rua B: AMARELO | Tempo: 2
(BFS) Visitando: Rua A: VERMELHO  | Rua B: AMARELO | Tempo no estado: 2
Rua A: VERMELHO  | Rua B: AMARELO | Tempo: 3
(BFS) Visitando: Rua A: VERMELHO  | Rua B: AMARELO | Tempo no estado: 3
Rua A: VERMELHO  | Rua B: AMARELO | Tempo: 4
(BFS) Visitando: Rua A: VERMELHO  | Rua B: AMARELO | Tempo no estado: 4
Rua A: VERMELHO  | Rua B: AMARELO | Tempo: 5
(BFS) Visitando: Rua A: VERMELHO  | Rua B: AMARELO | Tempo no estado: 5
```
