# 🧮 Sistema de Gerenciamento de IMC com Relatório Gráfico

## 📌 Sumário

- 📖 [Sobre o Projeto](#-sobre-o-projeto)
- 🎯 [Objetivos Técnicos](#-objetivos-técnicos)
- 🛠️ [Tecnologias Utilizadas](#️-tecnologias-utilizadas)
- ⚙️ [Funcionalidades Implementadas](#️-funcionalidades-implementadas)
- 🧠 [Arquitetura e Lógica Aplicada](#-arquitetura-e-lógica-aplicada)
- 🔄 [Fluxo do Sistema](#-fluxo-do-sistema)
- 📊 [Geração de Relatório](#-geração-de-relatório)
- 📂 [Estrutura do Projeto](#-estrutura-do-projeto)
- 🚀 [Possíveis Melhorias Futuras](#-possíveis-melhorias-futuras)
- 👨‍💻 [Autor](#-autor)

---

## 📖 Sobre o Projeto

Sistema desktop desenvolvido em **C# com Windows Forms**, responsável por realizar o gerenciamento completo de cadastros para cálculo de IMC (Índice de Massa Corporal).

O sistema permite:

- Cadastro de usuários
- Cálculo automático de IMC
- Classificação automática segundo padrões da OMS
- Consulta individual
- Alteração de registros
- Exclusão com confirmação
- Geração de relatório HTML com gráfico dinâmico

Os dados são armazenados em um arquivo `arquivo.json`, manipulados manualmente via leitura e escrita com `File.ReadAllLines` e `File.WriteAllText`.

---

## 🎯 Objetivos Técnicos

- Aplicar lógica de programação estruturada
- Trabalhar com manipulação de arquivos JSON sem bibliotecas externas
- Desenvolver um CRUD completo
- Implementar validações robustas de entrada
- Gerar relatórios automáticos em HTML
- Calcular médias por classificação
- Manipular múltiplos painéis dinamicamente

---

## 🛠️ Tecnologias Utilizadas

- C#
- .NET Framework
- Windows Forms
- Manipulação de arquivos com `System.IO`
- Geração de HTML dinâmico
- Estruturas condicionais e vetores para cálculo estatístico

---

## ⚙️ Funcionalidades Implementadas

✔ Cadastro de usuário (Nome, Peso, Altura)  
✔ Cálculo automático do IMC  
✔ Classificação automática (Magreza, Saudável, Sobrepeso, etc.)  
✔ Consulta por ID  
✔ Alteração de cadastro existente  
✔ Exclusão com confirmação  
✔ Listagem dinâmica no ListBox  
✔ Geração de relatório estatístico em HTML  
✔ Cálculo de média de IMC por classificação  

---

## 🧠 Arquitetura e Lógica Aplicada

O sistema trabalha com:

- Manipulação manual de JSON linha por linha
- Extração de valores via parsing de string
- Cálculo estatístico utilizando arrays
- Controle de estado da interface por `Panels`
- Uso de placeholders personalizados
- Validação com `TryParse`
- Controle de exceções lógicas

### Método de Classificação

O método `identificarClassificacao(float imc)` aplica as seguintes regras:

- IMC < 18.5 → Magreza  
- 18.5 a 24.9 → Saudável  
- 25 a 29.9 → Sobrepeso  
- 30 a 34.9 → Obesidade Grau I  
- 35 a 39.9 → Obesidade Grau II  
- ≥ 40 → Obesidade Grau III  

---

## 🔄 Fluxo do Sistema

1️⃣ Usuário acessa painel principal  
2️⃣ Escolhe operação (Cadastrar, Consultar, Alterar, Excluir)  
3️⃣ Sistema valida entradas  
4️⃣ JSON é atualizado manualmente  
5️⃣ Interface é atualizada dinamicamente  
6️⃣ Relatório pode ser gerado a qualquer momento  

---

## 📊 Geração de Relatório

O botão **Relatório**:

- Lê todos os registros do JSON
- Agrupa por classificação
- Calcula média de IMC por grupo
- Injeta os dados dinamicamente em `relatorio.html`
- Gera gráfico estatístico automaticamente

Isso demonstra:

- Manipulação de dados estruturados
- Cálculo estatístico
- Geração de conteúdo dinâmico

---

## 📂 Estrutura do Projeto

```
ProjetoWagner_4Bimestre
 ┣ 📜 Form1.cs
 ┣ 📜 Form1.Designer.cs
 ┣ 📜 Program.cs
 ┣ 📜 arquivo.json
 ┗ 📜 relatorio.html
```

A lógica principal está concentrada no `Form1.cs`, responsável pelo controle da interface e processamento das regras de negócio.

---

## 🚀 Possíveis Melhorias Futuras

- Utilização de biblioteca JSON (ex: System.Text.Json)
- Separação da lógica de negócio em classes próprias
- Implementação de banco de dados (SQL Server ou SQLite)
- Aplicação de padrão MVC
- Melhor tratamento de exceções
- Interface com design mais moderno
- Exportação de relatório em PDF
- Dashboard estatístico interno
