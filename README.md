# WJPSoar – Water Jug Problem em Soar

Este repositório contém uma implementação do clássico **Water Jug Problem** utilizando o sistema cognitivo **Soar**.

O objetivo do problema é manipular dois jarros com capacidades distintas até atingir um volume específico no jarro principal.

---

## 📌 Descrição do Problema

O sistema possui dois jarros:

- **j1**: capacidade de 100 litros (inicia com 100L)
- **j2**: capacidade de 20 litros (inicia com 20L)

### 🎯 Objetivo

Obter exatamente **60 litros no jarro j1**.

O sistema deve encontrar uma sequência válida de operações que leve do estado inicial ao estado objetivo.

---

## ⚙️ Operadores Implementados

O agente Soar utiliza os seguintes operadores:

### 🔹 `initialize-water-jug`
Inicializa o estado do problema com os dois jarros e seus volumes iniciais.

---

### 🔹 `fill`
Enche completamente um jarro até sua capacidade máxima.

---

### 🔹 `empty`
Esvazia completamente um jarro.

---

### 🔹 `pour`
Despeja água de um jarro para outro, respeitando:
- Capacidade máxima do jarro destino
- Quantidade disponível no jarro origem

Existem dois casos tratados:
- Fonte esvazia completamente
- Destino enche completamente

---

## 🧠 Estratégias de Controle

Foram implementadas regras de seleção para evitar ciclos e ações redundantes:

- Evita `fill` logo após `empty` no mesmo jarro
- Evita `empty` logo após `fill` no mesmo jarro
- Evita realizar um `pour` reverso imediato

Também é mantido o registro do último operador executado para controle da busca.

---

## 🎯 Detecção do Objetivo

O problema é considerado resolvido quando:

```

j1 = 60L

```

Ao atingir essa condição, o sistema imprime:

```

========================================
PROBLEMA RESOLVIDO!
===================

```

e encerra a execução.

---

## 📊 Monitoramento

O sistema imprime:

- Estado atual dos jarros a cada ciclo
- Operador aplicado
- Valores antes da aplicação da ação

Exemplo de saída:

```

Estado: j1=100L j2=20L
-> DESPEJAR de j1 (100L) para j2 (20L)

```

---

## 📂 Estrutura do Código

As produções estão organizadas nas seguintes categorias:

- `propose` – propõe operadores
- `apply` – aplica operadores
- `select` – controla a escolha entre operadores
- `elaborate` – calcula atributos derivados (ex: espaço vazio)
- `monitor` – imprime informações de execução
- `detect` – detecta estado objetivo

---

## 🛠️ Requisitos

- Soar Cognitive Architecture
- Ambiente compatível com execução de produções `.soar`

---

## 📚 Referência Conceitual

O problema dos jarros é um clássico da Inteligência Artificial simbólica, frequentemente utilizado para demonstrar:

- Busca em espaço de estados
- Representação de conhecimento
- Controle por produções
- Resolução de problemas em arquiteturas cognitivas

---

## 👤 Autor

Vitor Souza  
IME

---

## 📄 Licença

Uso acadêmico.

