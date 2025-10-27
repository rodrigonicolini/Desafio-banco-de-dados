# 📦 Projeto Lógico de Banco de Dados – Sistema de Contas, Pagamentos e Entregas

## 🧠 Visão Geral

Este projeto apresenta o esquema lógico de um banco de dados relacional voltado para o gerenciamento de contas de clientes, formas de pagamento e entregas. O objetivo é fornecer uma estrutura clara e funcional para armazenar, consultar e analisar dados relacionados a clientes (Pessoa Física e Jurídica), transações financeiras e logística de entregas.

## 🏗️ Estrutura do Esquema Lógico

O banco de dados é composto pelas seguintes entidades principais:

### 1. Cliente
- Representa os dados cadastrais de clientes.
- Pode ser do tipo **PF (Pessoa Física)** ou **PJ (Pessoa Jurídica)**, mas nunca ambos.
- **Campos**: `id_cliente`, `tipo_cliente`, `nome`, `cpf_cnpj`.

### 2. Conta
- Cada cliente possui uma ou mais contas.
- Relaciona-se diretamente com a tabela Cliente.
- **Campos**: `id_conta`, `id_cliente`, `data_criacao`.

### 3. Pagamento
- Armazena os registros de pagamento realizados em uma conta.
- Suporta múltiplas formas de pagamento por conta.
- **Campos**: `id_pagamento`, `id_conta`, `forma_pagamento`, `valor`, `data_pagamento`.

### 4. Entrega
- Registra o status e rastreamento de entregas associadas a uma conta.
- **Campos**: `id_entrega`, `id_conta`, `status`, `codigo_rastreio`, `data_entrega`.

## 🔍 Funcionalidades e Consultas

O projeto contempla diversas consultas SQL que demonstram o uso de cláusulas fundamentais:

- **SELECT**: Recuperação simples de dados.
- **WHERE**: Filtros por status, tipo de cliente, etc.
- **ORDER BY**: Ordenação por valor, data ou nome.
- **EXPRESSÕES DERIVADAS**: Cálculo de totais e agregações.
- **HAVING**: Filtros aplicados a grupos agregados.
- **JOINs**: Junções entre tabelas para análises mais complexas.

### Exemplos de perguntas respondidas pelas consultas:
- Quais clientes são do tipo PJ?
- Quais contas tiveram pagamentos acima de R$100?
- Qual o status atual das entregas?
- Quais formas de pagamento foram utilizadas por cada cliente?

## 🧪 Testes e Dados Simulados

O projeto inclui scripts de inserção de dados simulados para testes e validação das consultas. Os dados contemplam diferentes tipos de clientes, formas de pagamento e entregas com status variados.

## 📌 Considerações

- O modelo garante integridade referencial entre as tabelas.
- Respeita as regras de negócio: exclusividade de tipo de cliente, múltiplos pagamentos por conta, e rastreabilidade de entregas.
- Pode ser expandido para incluir produtos, notas fiscais, ou integração com sistemas externos.
