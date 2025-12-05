# 🍔 Sistema de Gerenciamento de Pedidos (Console App)

[![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat-square&logo=python)](https://www.python.org/)
[![Type-CLI](https://img.shields.io/badge/Interface-CLI-333333?style=flat-square)](https://docs.python.org/3/library/cmd.html)
[![Storage-File](https://img.shields.io/badge/Storage-TXT%20File-4CAF50?style=flat-square)](https://docs.python.org/3/library/os.html)

## 📝 Descrição do Projeto

Este é um aplicativo de console simples, desenvolvido em **Python**, para simular o gerenciamento de pedidos de uma lanchonete. O sistema permite criar, gerenciar, visualizar e cancelar pedidos. A persistência dos dados dos clientes (CPF, nome e senha) e dos itens pedidos é realizada através de um arquivo de texto (`pedidos.txt`).

O projeto é ideal para demonstrar o uso de coleções de dados (dicionários e listas) e manipulação de arquivos no Python, incluindo operações de leitura, escrita e exclusão.

---

## ✨ Funcionalidades

O sistema oferece as seguintes opções no menu principal (`main()`):

| Código | Descrição | Funções Principais |
| :---: | :--- | :--- |
| `1` | **Novo Pedido:** Cria um novo registro de pedido (usuário) em `pedidos.txt`. | `novo_pedido()`, `criar_usuario()` |
| `2` | **Cancelar Pedido:** Remove o pedido completo e o registro do cliente. | `cancela_pedido()`, `excluir_usuario()` |
| `3` | **Inserir Produto:** Adiciona itens ao pedido existente após validação de login. | `insere_produto()`, `adicionar_produto()` |
| `4` | **Cancelar Produto:** Registra a remoção de uma quantidade específica de um item. | `cancela_produto()`, `adicionar_produto()` |
| `5` | **Valor do Pedido:** Exibe o valor total a pagar. | `valor_do_pedido()`, `calcula_total()` |
| `6` | **Extrato do Pedido:** Mostra o detalhe completo, incluindo histórico de cancelamentos. | `extrato_do_pedido()`, `mostra_extrato()` |
| `0` | **Sair:** Encerra a aplicação. | |

## 🍽️ Cardápio (Produtos)

O cardápio está definido no dicionário `PRODUTOS`.

| Código | Nome | Preço |
| :---: | :---: | :---: |
| 1 | X-salada | R$ 10.00 |
| 2 | X-burger | R$ 10.00 |
| 3 | Cachorro quente | R$ 7.50 |
| 4 | Misto quente | R$ 8.00 |
| 5 | Salada de frutas | R$ 5.50 |
| 6 | Refrigerante | R$ 4.50 |
| 7 | Suco natural | R$ 6.25 |

---

## 💾 Persistência de Dados (`pedidos.txt`)

O sistema armazena todos os pedidos ativos no arquivo `pedidos.txt`.

### Estrutura do Arquivo

Cada pedido é separado por duas quebras de linha (`\n\n`) e segue o formato:

1.  CPF do Cliente
2.  Nome do Cliente
3.  Senha de Acesso
4.  Itens do Pedido (código,quantidade)

> **Nota sobre Cancelamento:** Quando um produto é cancelado, ele é registrado no arquivo com uma **quantidade negativa** (ex: `1,-1`). Isso permite que a função `mostra_extrato` exiba o histórico completo das transações, enquanto a função `calcula_total` garante que apenas o saldo final seja cobrado.

---

## ⚙️ Execução

### Pré-requisitos

* **Python 3.x** instalado.
* As bibliotecas `datetime`, `os` e `math` (embora `math` não seja utilizada no código fornecido) são módulos padrão do Python e não requerem instalação via `pip`.

### Como Iniciar

1.  Salve o código como `sistema_pedidos.py`.
2.  Execute o script a partir do terminal:

```bash
python sistema_pedidos.py
