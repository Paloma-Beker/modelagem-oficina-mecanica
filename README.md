# 🚗 Projeto de Modelagem Conceitual – Oficina Mecânica

Este projeto foi desenvolvido como parte de um desafio do bootcamp de Análise de Dados. A proposta consiste em criar um **modelo conceitual (diagrama ER)** para um sistema de controle e gerenciamento de ordens de serviço em uma oficina mecânica.

---

## 🧾 Narrativa

> Clientes levam veículos à oficina mecânica para conserto ou revisões. Cada veículo é designado a uma equipe de mecânicos, que avalia os serviços a serem realizados. Uma ordem de serviço é gerada com data de entrega, e o custo total é calculado com base na mão de obra e nas peças utilizadas. O cliente autoriza a execução dos serviços, que são então realizados pela equipe. Os pagamentos são registrados ao final do processo.

---

## 🧱 Entidades e Atributos

- **cliente**: nome/razão social, CPF/CNPJ, telefone, endereço
- **veiculo**: informações sobre revisões, trocas de peças e consertos
- **cliente_veiculo**: relacionamento N:M entre cliente e veículo com tipo de vínculo
- **ordemServico**: número, status_ordem ENUM('pendente', 'em_execucao', 'concluida', 'cancelada'), vínculo com cliente, veículo, equipe, pagamento
- **servico**: tipo, valor da mão de obra, quantidade, autorização do cliente (`autorizacao_cliente` como `TINYINT`)
- **peca**: tipo, valor, quantidade, autorização do cliente
- **equipeMecanica**: código, nome, endereço, especialidade
- **pagamento**: data, forma, valor, status_pagamento ENUM('aguardando', 'confirmado', 'recusado', 'estornado'), nota fiscal

---

## 🔁 Relacionamentos

- Um cliente pode ter um ou mais veículos (via `cliente_veiculo`)
- Um veículo pode gerar várias ordens de serviço
- Cada ordem é associada a uma equipe de mecânicos
- Cada ordem está relacionada a um conjunto de serviços, peças e um pagamento

---

## 💡 Justificativa de Modelagem

- Os nomes foram padronizados sem espaços ou acentos para garantir compatibilidade com SQL.
- cliente_veiculo permite representar vínculos como copropriedade ou uso empresarial.
- Atributos de controle como status_ordem e status_pagamento usam `ENUM` para garantir integridade semântica.
- Atributos booleanos, como autorizacao_cliente, usam `TINYINT(1)`, conforme o padrão do MySQL.
- A estrutura garante rastreabilidade, normalização e preparo para uso futuro em BI ou sistemas relacionais.

---

## 📁 Estrutura de Arquivos

- `Modelagem Conceitual Mecancia.png`: Imagem do diagrama ER
- `relatorio_modelagem_oficina.pdf`: Relatório com análise e justificativas

---

## 👩‍💻 Autora

**Paloma Beker**  
Estudante de Ciência de Dados | Bootcamp de Análise de Dados  
[LinkedIn](https://www.linkedin.com/in/paloma-beker)

---

## ✅ Conclusão

Este projeto apresenta uma modelagem robusta e prática de um sistema de ordens de serviço para oficinas mecânicas. A modelagem pode ser implementada em um SGBD relacional, com potencial para futuras análises de dados.

