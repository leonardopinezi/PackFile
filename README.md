# ⚙️ PackFile  
**PackFile** é uma linguagem de automação minimalista voltada para **builds, execução de código e tarefas de sistema**.  
Ela combina uma sintaxe simples — inspirada em Assembly e Batch — com o poder do Node.js, permitindo criar **scripts automatizados, repetíveis e claros**.

---

## 🧠 Conceito
Com **PackFile**, você pode criar scripts que:
- Automatizam **compilações**, **execuções** e **empacotamentos**;  
- Controlam **fluxos de lógica simples** (comparações, saltos, loops);  
- Integram **comandos do sistema operacional** diretamente.

---

## 📘 Sintaxe e Comandos

| Comando | Sintaxe | Descrição |
|----------|----------|-----------|
| `SET` | `SET <VARIÁVEL> <VALOR>` | Cria ou altera uma variável |
| `ECHO` | `ECHO <TEXTO>` | Exibe uma mensagem no terminal |
| `END` | `END` | Finaliza a execução do script |
| `CLEAN` | `CLEAN` | Limpa o console |
| `SUM` | `SUM <NUM1> <NUM2> <VAR>` | Soma dois valores e armazena o resultado |
| `SUB` | `SUB <NUM1> <NUM2> <VAR>` | Subtrai dois valores e armazena o resultado |
| `#` | `# <COMENTÁRIO>` | Comentário — ignorado na execução |
| `SPAWN` | `SPAWN <COMANDO>` | Executa um comando do sistema operacional |
| `IF=` | `IF= <VALOR1> : <VALOR2>` | Executa a próxima linha **somente se** os valores forem iguais |
| `IF!=` | `IF!= <VALOR1> : <VALOR2>` | Executa a próxima linha **somente se** os valores **forem diferentes** |

---

## 🧩 Exemplo 1 — “Hello, World!”

```bash
# Define uma variável chamada MSG com o valor "Hello,"
SET MSG Hello,
# Exibe a variável (*MSG) e a palavra "World"
ECHO *MSG World

# Encerra o programa
END
```

**Saída esperada:**
```
Hello, World
```

---

## 🛠️ Exemplo 2 — Compilação Automática

```bash
CLEAN
SET SRC main.c
SET OUT app

ECHO Compilando *SRC...
SPAWN gcc *SRC -o *OUT

IF= 0 : 0
    ECHO Compilação concluída!

END
```

**Explicação:**
- Define arquivos de entrada e saída  
- Compila um código em C  
- Mostra mensagem de sucesso  
- Executa o programa gerado  

---

## 💡 Dica
Você pode **usar variáveis com o prefixo `*`** para expandir valores armazenados.  
Exemplo:
```bash
SET NAME Leonardo
ECHO Hello *NAME
```
🡒 imprime → `Hello Leonardo`

---

## 🧱 Estrutura Interna
- Desenvolvida em **Node.js**
- Arquivos de script são nomeados **`PackFile`**
- Sintaxe **line-based**, fácil de interpretar e expandir
- Suporte a **labels e saltos** (`:` e `>`)

---

## 🚀 Ideias de Uso
- Automatizar builds de Projetos  
- Gerar relatórios e logs  
- Compilar múltiplos projetos em sequência  
- Criar ferramentas DevOps minimalistas  
