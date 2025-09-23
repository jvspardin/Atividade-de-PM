># Atividade-de-PM
> nome: João Vítor Sàtiro Pardin - ADS

## Atividade baseada no Livro Entendendo Algoritmos
<hr>

## Algoritmo 1 - Busca Linear
```python
def busca_linear(lista, item):
    for i in range(len(lista)):
        if lista[i] == item:
            return i
    return None
```

## Algoritmo 2 - Busca Binária
```python
def busca_binaria(lista, item):
    inicio = 0
    fim = len(lista) - 1
    while inicio <= fim:
        meio = (inicio + fim) // 2
        chute = lista[meio]
        if chute == item:
            return meio
        elif chute < item:
            inicio = meio + 1
        else:
            fim = meio - 1

    return None
```

## Algoritmo 3 - Busca 
```python
def ordenacao_por_selecao(lista):
    n = len(lista)
    for i in range(n):
        menor_indice = i
        for j in range(i + 1, n):
            if lista[j] < lista[menor_indice]:
                menor_indice = j
        # Troca o menor elemento encontrado com o elemento da posição atual
        lista[i], lista[menor_indice] = lista[menor_indice], lista[i]
    return lista
```

