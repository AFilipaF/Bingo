# 🎱 Bingo em Python

Projeto Prático de Avaliação Diagnóstica — Python.
Um jogo de Bingo simplificado, jogado na consola, com apostas, prémios e probabilidades aleatórias.

## Objetivo

Simular uma partida de Bingo entre vários jogadores, cada um com os seus próprios cartões,
onde os números são chamados aleatoriamente até alguém completar o cartão (Bingo). Ao longo
do jogo é também atribuído um prémio mais pequeno a quem completar primeiro uma linha.

## Como jogar

1. Corre o programa:
   ```
   python bingo.py
   ```
2. **Criação de jogadores**: para cada jogador, indica o nome e quantos cartões quer
   comprar (entre 1 e 3, a 1€ cada). Repete até responderes "n" a "Novo jogador?".
3. **Consultar cartões**: podes escrever o nome de um jogador para veres os cartões
   dele, ou carregar ENTER para avançar sem consultar nenhum.
4. **Sorteio**: o jogo vai chamando números aleatórios, um a um, marcando-os nos
   cartões onde aparecem. Depois de cada número, carrega ENTER para ver o seguinte.
5. **Prémios**:
   - **Linha** — a primeira vez que alguém completa uma linha (3×5) num cartão,
     recebe 10% do valor total apostado (dividido, se mais que um jogador fizer
     linha ao mesmo tempo).
   - **Bingo** — quando um cartão fica completamente preenchido, o jogo termina e
     esse(s) jogador(es) recebem o valor restante do prémio.
6. No final, podes escolher iniciar um **novo jogo** (recomeça tudo do zero, com
   novos jogadores) ou terminar o programa.

## Regras principais

- Cada jogador começa com 10€ de saldo.
- Cada cartão custa 1€ e tem 15 números únicos (0–99), dispostos numa grelha de
  3 linhas por 5 colunas.
- Um jogador tem de comprar pelo menos 1 cartão (e no máximo 3) para poder jogar.
- O valor de todos os cartões comprados forma o "Prémio" do jogo.
- O prémio de Linha só é atribuído uma vez por jogo; o de Bingo fecha o jogo.

## Estrutura do código

| Função | O que faz |
|---|---|
| `gerar_cartao(jogador)` | Cria um cartão novo, com 15 números aleatórios e únicos, em grelha 3×5 |
| `verificar_linha(cartao)` | Verifica se alguma das 3 linhas do cartão está completa |
| `verificar_bingo(cartao)` | Verifica se o cartão está completamente preenchido |
| `mostrar_cartao(cartao)` | Imprime a grelha do cartão, mostrando os números já marcados e `-` nos restantes |

Os dados de cada **jogador** (`nome`, `saldo`, `cartoes`) e de cada **cartão**
(`jogador`, `numeros`, `marcados`) são guardados em dicionários, e a lista
`id_jogadores` junta todos os jogadores em jogo.

## Requisitos

- Python 3
- Nenhuma biblioteca externa — usa apenas o módulo `random`, incluído no Python.

## Possíveis melhorias futuras

- Guardar o histórico de jogos anteriores.
- Interface gráfica em vez de consola.
