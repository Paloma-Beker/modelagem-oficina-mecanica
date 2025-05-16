# 🚗 Projeto de Modelagem Conceitual – Oficina Mecânica

Este projeto foi desenvolvido como parte de um desafio do bootcamp de Análise de Dados. A proposta consiste em criar um **modelo conceitual (diagrama ER)** para um sistema de controle e gerenciamento de ordens de serviço em uma oficina mecânica.

---

## 🧾 Narrativa

> Clientes levam veículos à oficina mecânica para conserto ou revisões. Cada veículo é designado a uma equipe de mecânicos, que avalia os serviços a serem realizados. Uma ordem de serviço é gerada com data de entrega, e o custo total é calculado com base na mão de obra e nas peças utilizadas. O cliente autoriza a execução dos serviços, que são então realizados pela equipe. Os pagamentos são registrados ao final do processo.

---

## 🧱 Entidades e Atributos

- **Cliente**: Nome/Razão Social, CPF/CNPJ, Telefone, Endereço
- **Veículo**: Revisão Periódica, Troca de Peças, Consertos
- **ClienteVeiculo**: Relacionamento N:M entre cliente e veículo
- **EquipeMecanica**: Nome, Código Identificador, Endereço, Especialidade
- **OrdemServico**: ID, Status, Serviço Prestado, Peças utilizadas, Veículo, Equipe
- **Serviço**: Tipo, Valor, Quantidade, Datas, Autorização do cliente
- **Peça**: Tipo, Valor, Quantidade, Datas, Autorização do cliente
- **Pagamento**: Data, Forma, Valor, Status, Nota fiscal

---

## 🔁 Relacionamentos

- Cliente possui um ou mais veículos (via ClienteVeiculo)
- Veículo pode ter várias ordens de serviço
- Cada ordem é executada por uma equipe
- Cada ordem possui serviços, peças e pagamento

---

## 💡 Justificativa de Modelagem

A modelagem foi baseada na narrativa do sistema de ordens de serviço de uma oficina, priorizando clareza, normalização e representação fiel do contexto real.

- **Cliente** unifica pessoa física e jurídica, evitando duplicidade de entidades.  
- **ClienteVeiculo** permite relacionamentos N:M entre clientes e veículos.  
- **Ordem de Serviço** centraliza as informações de execução, vinculando veículo, equipe, serviços, peças e pagamento.  
- **Serviço** e **Peça** foram separados para controle individual de custos.  
- **Pagamento** registra dados completos (data, forma, valor e status), garantindo rastreabilidade.  

Essa estrutura facilita consultas, relatórios e futura implementação do sistema em um banco relacional.

---

## 👩‍💻 Autora

Paloma Beker  
Estudante de Ciência de Dados | Bootcamp de Análise de Dados  
[LinkedIn](https://www.linkedin.com/in/paloma-beker)

---

## 📎 Arquivos

- `Modelagem Conceitual Mecancia.png`: Diagrama ER do projeto
- `Relatorio Modelagem Oficina Mecanica.pdf`: Documento com análise e justificativas
