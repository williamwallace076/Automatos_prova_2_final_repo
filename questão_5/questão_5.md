## Questão 5

Nessa resolução, a Máquina de Turing aplica a função $f(m,n) = \max(m-n, 0)$, onde $m$ e $n$ equivalem a números naturais representados na fita por meio da notação unária $1^m01^n$.

O autômato gerado opera com base em um **pareamento de símbolos**, seguindo a lógica de cancelamento mútuo:

1. **Leitura e Marcação:** Para cada símbolo `1` localizado no primeiro bloco ($1^m$), a máquina move-se para a direita e cruza o separador `0`.
2. **Cancelamento:** O sistema busca um símbolo `1` correspondente no segundo bloco ($1^n$) para ser apagado (substituído pelo símbolo branco `_`).
3. **Ciclo:** Esse processo é repetido ciclicamente até que um dos blocos seja completamente consumido.

### 🏁 Estados Finais da Fita

Ao término da execução, o comportamento do autômato divide-se em dois cenários distintos:

* **Se $m > n$:** A máquina remove o separador `0`, limpa os símbolos temporários e preserva na fita apenas o restante dos símbolos `1` não pareados, resultando na configuração final $1^{m-n}$.
* **Se $m \le n$:** O primeiro bloco se esgota antes ou ao mesmo tempo que o segundo. A máquina limpa todos os símbolos remanescentes e finaliza a computação com a fita inteiramente em branco.
