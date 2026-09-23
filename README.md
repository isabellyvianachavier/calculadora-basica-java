# Calculadora Java v2.0

Refatoração de uma calculadora de terminal em Java, evoluindo de um único método monolítico para uma estrutura organizada.

## Sobre o projeto

A versão original (v1.0) concentrava toda a lógica — leitura de entrada, cálculo e histórico — dentro de um único `main()`, com um `switch` que crescia a cada nova operação adicionada.

A v2.0 reorganiza o código em três partes:

- **`Operacao`** (`enum`) — define as operações disponíveis e como cada uma calcula seu resultado, usando `BiFunction`. Cada operação é responsável por sua própria lógica (incluindo validações, como a divisão por zero).
- **`Historico`** — responsável por registrar e exibir as operações realizadas.
- **`main`** — orquestra o fluxo: lê a entrada do usuário, localiza a operação no `HashMap` e delega o cálculo e o registro.

## Operações disponíveis

| Símbolo | Operação         |
|---------|------------------|
| `+`     | Soma             |
| `-`     | Subtração        |
| `*`     | Multiplicação    |
| `/`     | Divisão          |
| `pow`   | Potenciação      |
| `%`     | Resto da divisão |
| `max`   | Maior valor      |
| `min`   | Menor valor      |

## Como usar

```bash
java Main.java
```

Comandos disponíveis no terminal:

- `ENTER` — inicia uma nova operação
- `-h` — exibe o histórico de operações
- `.exit` — encerra o programa

## Por que a refatoração?

Para projeto de aula de java, separar o código dessa forma torna a aplicação mais fácil de estender: adicionar uma nova operação que exige apenas uma nova linha no `enum` `Operacao`, sem tocar no `main` ou no `Historico`.
