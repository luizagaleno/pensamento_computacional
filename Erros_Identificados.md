# Erros Identificados

## 📌 Introdução

Durante a análise do projeto, foram identificados três categorias principais de erros que comprometiam o funcionamento correto do sistema. Esses erros variam em severidade e dificuldade de detecção.

---

## 1️⃣ Erros de Sintaxe

Erros de sintaxe são os mais óbvios, pois impedem completamente a execução do código. Eles são causados por escrever os comandos de forma incorreta.

### Problemas Identificados:

- ❌ Falta de `:` em estruturas condicionais
- ❌ Parênteses não fechados
- ❌ Problemas de indentação
- ❌ Variáveis escritas de forma incorreta
- ❌ Aspas não balanceadas
- ❌ Operadores mal utilizados

### Exemplo 1: Falta de Dois-Pontos

**Código com erro:**
```python
if usuario == "admin"
    print("Acesso permitido")
```

**Problema:** Falta de `:` no final da condição `if`

**Mensagem de erro:**
```
SyntaxError: invalid syntax
```

### Exemplo 2: Parênteses Não Fechados

**Código com erro:**
```python
print("Olá mundo"
```

**Problema:** Parêntese de fechamento não foi adicionado

**Mensagem de erro:**
```
SyntaxError: unexpected EOF while parsing
```

### Exemplo 3: Indentação Incorreta

**Código com erro:**
```python
for i in range(5):
print(i)
```

**Problema:** O código dentro do loop não está indentado

**Mensagem de erro:**
```
IndentationError: expected an indented block
```

---

## 2️⃣ Erros de Lógica

Erros de lógica são mais difíceis de detectar porque o código executa sem problemas, mas os resultados estão incorretos.

### Problemas Identificados:

- ❌ Condições invertidas
- ❌ Informações exibidas incorretamente
- ❌ Fluxos de decisão errados
- ❌ Operadores lógicos mal utilizados
- ❌ Comparações incorretas
- ❌ Valores iniciais errados

### Exemplo 1: Condição Invertida

**Código com erro:**
```python
idade = 16

if idade >= 18:
    print("Menor de idade")
else:
    print("Maior de idade")
```

**Problema:** A lógica está correta, mas as mensagens estão invertidas. O código diz "Menor de idade" para maiores de 18 anos.

**Resultado:** Saída incorreta para o usuário

### Exemplo 2: Operador Lógico Errado

**Código com erro:**
```python
score = 85

if score < 60 or score >= 90:
    print("Aprovado")
else:
    print("Reprovado")
```

**Problema:** A condição deveria ser `and` para verificar se a nota está entre 60 e 90, não `or`.

### Exemplo 3: Inicialização de Variável Incorreta

**Código com erro:**
```python
total = 10  # Deveria ser 0
for numero in [1, 2, 3, 4, 5]:
    total += numero
print(total)  # Resultado: 25 (esperado: 15)
```

**Problema:** A variável `total` foi inicializada com 10 em vez de 0.

---

## 3️⃣ Erros de Execução

Erros de execução ocorrem quando o programa está rodando e o usuário fornece dados inválidos ou ocorre uma situação inesperada.

### Problemas Identificados:

- ❌ Divisão por zero
- ❌ Entrada de letras no lugar de números
- ❌ Variáveis não definidas
- ❌ Falhas na leitura de arquivos
- ❌ Índice fora do alcance (list index out of range)
- ❌ Conversão de tipo inválida

### Exemplo 1: Divisão por Zero

**Código com erro:**
```python
numero = int(input("Digite um número: "))
resultado = 10 / numero
print(resultado)
```

**Problema:** Se o usuário digitar `0`, o programa vai gerar um erro `ZeroDivisionError`

**Mensagem de erro:**
```
ZeroDivisionError: division by zero
```

### Exemplo 2: Entrada Inválida (Não Numérica)

**Código com erro:**
```python
idade = int(input("Qual sua idade? "))
print(f"Você tem {idade} anos")
```

**Problema:** Se o usuário digitar `abc` em vez de um número, o programa vai gerar um erro

**Mensagem de erro:**
```
ValueError: invalid literal for int() with base 10: 'abc'
```

### Exemplo 3: Índice Fora do Alcance

**Código com erro:**
```python
numeros = [1, 2, 3]
print(numeros[10])  # A lista tem apenas 3 elementos
```

**Problema:** Tentativa de acessar um índice que não existe na lista

**Mensagem de erro:**
```
IndexError: list index out of range
```

### Exemplo 4: Arquivo Não Encontrado

**Código com erro:**
```python
arquivo = open("dados.txt", "r")
conteudo = arquivo.read()
arquivo.close()
```

**Problema:** Se o arquivo `dados.txt` não existir, será gerado um erro

**Mensagem de erro:**
```
FileNotFoundError: [Errno 2] No such file or directory: 'dados.txt'
```

---

## 📊 Resumo dos Erros

| Tipo de Erro | Severidade | Detecção | Exemplos |
|---|---|---|---|
| **Sintaxe** | 🔴 Crítica | Imediata | Falta de `:`, parênteses não fechados |
| **Lógica** | 🟡 Alta | Difícil | Condições invertidas, operadores errados |
| **Execução** | 🟠 Média | Variável | Divisão por zero, entrada inválida |

---

## 🎯 Próximos Passos

Consulte o arquivo **Projeto_Corrigido.md** para ver como cada um desses erros foi corrigido e as justificativas por trás de cada solução.
