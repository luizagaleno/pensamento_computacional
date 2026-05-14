# Projeto Corrigido

## 📌 Introdução

Este documento apresenta as correções realizadas nos erros identificados, incluindo o código corrigido e as justificativas para cada mudança.

---

## 1️⃣ Correção de Erros de Sintaxe

### Correção 1: Falta de Dois-Pontos

**Código com erro:**
```python
if usuario == "admin"
    print("Acesso permitido")
```

**Código corrigido:**
```python
if usuario == "admin":
    print("Acesso permitido")
```

**Justificativa:**
Em Python, toda estrutura condicional (`if`, `elif`, `else`), loop (`for`, `while`), definição de função (`def`) ou classe (`class`) deve terminar com um **dois-pontos** (`:`). Este símbolo indica ao interpretador Python que um bloco de código indentado virá a seguir.

---

### Correção 2: Parênteses Não Fechados

**Código com erro:**
```python
nomes = ["Ana", "Bruno", "Carlos"
print(nomes)
```

**Código corrigido:**
```python
nomes = ["Ana", "Bruno", "Carlos"]
print(nomes)
```

**Justificativa:**
Toda estrutura que abre um parêntese `(`, colchete `[` ou chave `{` deve ser fechada. O Python não consegue interpretar o código se houver um desequilíbrio entre aberturas e fechamentos.

---

### Correção 3: Indentação Incorreta

**Código com erro:**
```python
for i in range(5):
print(i)
```

**Código corrigido:**
```python
for i in range(5):
    print(i)
```

**Justificativa:**
A indentação em Python não é apenas uma questão de estilo — é **obrigatória** para delimitar blocos de código. Todo código que faz parte de um loop, condicional ou função deve estar indentado com espaços ou tabulações (geralmente 4 espaços).

---

### Correção 4: Variável com Nome Errado

**Código com erro:**
```python
idade = 25
print(idad)  # Falta um 'e'
```

**Código corrigido:**
```python
idade = 25
print(idade)
```

**Justificativa:**
Python é sensível a maiúsculas e minúsculas. Se a variável foi definida como `idade`, deve ser referenciada exatamente assim. Erros tipográficos causam `NameError`.

---

## 2️⃣ Correção de Erros de Lógica

### Correção 1: Condição Invertida

**Código com erro:**
```python
idade = 16

if idade >= 18:
    print("Menor de idade")
else:
    print("Maior de idade")
```

**Código corrigido:**
```python
idade = 16

if idade >= 18:
    print("Maior de idade")
else:
    print("Menor de idade")
```

**Justificativa:**
A lógica da condição estava correta (`if idade >= 18`), mas as mensagens estavam invertidas. Se a idade é maior ou igual a 18, o usuário é **maior de idade**, não menor. As mensagens dentro do `if` e `else` foram trocadas.

---

### Correção 2: Operador Lógico Errado

**Código com erro:**
```python
score = 85

if score < 60 or score >= 90:
    print("Aprovado")
else:
    print("Reprovado")
```

**Resultado esperado para score = 85:** Reprovado  
**Resultado atual:** Reprovado ✓  

**Análise:** Na verdade, esse exemplo estava funcionando corretamente, mas a lógica poderia ser confusa. Vamos melhorar:

**Código melhorado:**
```python
score = 85

if score >= 60 and score < 90:
    print("Aprovado")
elif score >= 90:
    print("Aprovado com distinção")
else:
    print("Reprovado")
```

**Justificativa:**
A utilização de `and` torna a lógica mais clara e explícita. A condição agora verifica se o score está entre 60 e 90 (aprovação normal) ou acima de 90 (aprovação com distinção).

---

### Correção 3: Inicialização de Variável Incorreta

**Código com erro:**
```python
total = 10  # Valor inicial errado
for numero in [1, 2, 3, 4, 5]:
    total += numero
print(total)  # Resultado: 25 (esperado: 15)
```

**Código corrigido:**
```python
total = 0  # Valor inicial correto
for numero in [1, 2, 3, 4, 5]:
    total += numero
print(total)  # Resultado: 15 ✓
```

**Justificativa:**
Variáveis acumuladoras devem começar com o valor **neutro** para a operação. Para soma, o valor neutro é 0. Se começar com 10, todos os valores somados terão 10 adicionado ao resultado final.

---

## 3️⃣ Correção de Erros de Execução

### Correção 1: Divisão por Zero com Try/Except

**Código com erro:**
```python
numero = int(input("Digite um número: "))
resultado = 10 / numero
print(resultado)
```

**Código corrigido:**
```python
try:
    numero = int(input("Digite um número: "))
    if numero == 0:
        print("Erro: não é possível dividir por zero.")
    else:
        resultado = 10 / numero
        print(f"Resultado: {resultado}")
except ValueError:
    print("Erro: digite um número válido.")
except Exception as e:
    print(f"Erro inesperado: {e}")
```

**Justificativa:**
O bloco `try/except` captura erros durante a execução. Neste caso:
- `try`: Tenta executar o código
- `except ValueError`: Captura erros se o usuário não digitar um número
- `except Exception`: Captura qualquer outro erro inesperado
- Também verificamos se o número é 0 antes de dividir

---

### Correção 2: Entrada Inválida com Validação

**Código com erro:**
```python
idade = int(input("Qual sua idade? "))
print(f"Você tem {idade} anos")
```

**Código corrigido:**
```python
while True:
    try:
        idade = int(input("Qual sua idade? "))
        if idade < 0 or idade > 150:
            print("Erro: digite uma idade válida (0-150).")
            continue
        print(f"Você tem {idade} anos")
        break
    except ValueError:
        print("Erro: digite um número inteiro válido.")
```

**Justificativa:**
Além de tratarem erros de conversão com `try/except`, adicionamos:
- Loop `while True`: Continua pedindo até obter entrada válida
- Validação de range: Verifica se a idade está dentro de um intervalo razoável
- Mensagens claras: Orientam o usuário sobre o que fazer

---

### Correção 3: Índice Fora do Alcance

**Código com erro:**
```python
numeros = [1, 2, 3]
print(numeros[10])  # IndexError
```

**Código corrigido (Opção 1):**
```python
numeros = [1, 2, 3]
indice = 10

if 0 <= indice < len(numeros):
    print(numeros[indice])
else:
    print(f"Erro: índice {indice} fora do alcance (0-{len(numeros)-1}).")
```

**Código corrigido (Opção 2):**
```python
numeros = [1, 2, 3]
indice = 10

try:
    print(numeros[indice])
except IndexError:
    print(f"Erro: índice {indice} não existe na lista.")
```

**Justificativa:**
Existem duas abordagens:
1. **Verificação preventiva**: Verifica o índice antes de acessar
2. **Tratamento de exceção**: Captura o erro quando ocorre

A escolha depende do contexto, mas a verificação preventiva é geralmente mais eficiente.

---

### Correção 4: Arquivo Não Encontrado

**Código com erro:**
```python
arquivo = open("dados.txt", "r")
conteudo = arquivo.read()
arquivo.close()
print(conteudo)
```

**Código corrigido:**
```python
try:
    with open("dados.txt", "r") as arquivo:
        conteudo = arquivo.read()
        print(conteudo)
except FileNotFoundError:
    print("Erro: arquivo 'dados.txt' não encontrado.")
except IOError:
    print("Erro ao ler o arquivo.")
```

**Justificativa:**
Melhorias implementadas:
- `with` statement: Fecha automaticamente o arquivo, mesmo se houver erro
- `except FileNotFoundError`: Captura quando arquivo não existe
- `except IOError`: Captura problemas gerais de I/O
- Sem necessidade de `close()` manual

---

## 📊 Resumo das Correções

| Tipo de Erro | Solução Principal | Resultado |
|---|---|---|
| **Sintaxe** | Corrigir escrita e indentação | ✅ Código executa |
| **Lógica** | Revisar condições e operadores | ✅ Resultados corretos |
| **Execução** | Usar try/except e validação | ✅ Programa mais robusto |

---

## 🎯 Boas Práticas Aplicadas

✅ **Validação de entrada:** Sempre verifique dados inseridos pelo usuário  
✅ **Tratamento de exceções:** Use try/except para situações inesperadas  
✅ **Mensagens claras:** Informe ao usuário o que deu errado  
✅ **Código legível:** Use variáveis com nomes descritivos  
✅ **Testes:** Teste com entradas inválidas, casos extremos e situações normais  

---

## 📚 Próximos Passos

Consulte o arquivo **Avaliacao.md** para ler a análise crítica sobre a clareza, eficiência e escalabilidade das soluções implementadas.
