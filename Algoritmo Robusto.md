># Trabalho de PM
>Nome: João Vítor Sátiro Pardin -ADS 


# O exemplo do livro
```python
def busca_binaria(lista, item):
    baixo = 0
    alto = len(lista) - 1

    while baixo <= alto:
        meio = (baixo + alto) // 2
        chute = lista[meio]
        if chute == item:
            return meio
        if chute > item:
            alto = meio - 1
        else:
            baixo = meio + 1
    return None
```


🔹 # Versão Robusta


```python
from typing import List, Optional, TypeVar

T = TypeVar("T")  # Permite buscar em listas de qualquer tipo comparável (int, str, etc.)

def busca_binaria(lista: List[T], item: T) -> Optional[int]:
    """
    Realiza uma busca binária em uma lista ordenada.

    Args:
        lista (List[T]): Lista ordenada onde será feita a busca.
        item (T): Valor que se deseja encontrar.

    Returns:
        Optional[int]: Índice do item encontrado ou None se não estiver na lista.

    Raises:
        ValueError: Se a lista não estiver ordenada.
    """
    # ✅ Validação da lista
    if lista != sorted(lista):
        raise ValueError("A lista deve estar ordenada para usar busca binária.")

    baixo = 0
    alto = len(lista) - 1

    # ✅ Contador opcional de iterações (para depuração)
    iteracoes = 0

    while baixo <= alto:
        iteracoes += 1
        meio = (baixo + alto) // 2
        chute = lista[meio]

        if chute == item:
            print(f"Item encontrado após {iteracoes} iterações.")
            return meio
        elif chute > item:
            alto = meio - 1
        else:
            baixo = meio + 1

    print(f"Item não encontrado após {iteracoes} iterações.")
    return None
```
