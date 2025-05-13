**Raku** (anteriormente conhecido como **Perl 6**) é uma linguagem de programação moderna, poderosa e expressiva, projetada para ser **flexível**, **concisa** e **multiplataforma**. Ela não é um substituto direto do Perl 5, mas sim uma evolução separada, com sintaxe e paradigmas próprios.

---

## 🧩 Para que serve a linguagem **Raku**?

Raku é uma linguagem **multi-paradigma** que pode ser usada em várias áreas:

### ✅ **Principais usos:**

1. **Automação de tarefas** (como scripts em shell, mas mais avançados)
2. **Manipulação de texto** (forte suporte a regex, superior até ao Perl tradicional)
3. **Desenvolvimento web**
4. **Processamento de dados e logs**
5. **Prototipagem rápida**
6. **Programação funcional, OO e concorrente**
7. **Metaprogramação e DSLs (Domain-Specific Languages)**

---

## 🚀 Como usar Raku

### 🔧 1. **Instalação**

#### No Linux/macOS:

```bash
# Instalar via rakubrew (gerenciador)
curl -s https://raw.githubusercontent.com/rakubrew/rakubrew/master/bootstrap | bash

# Ative um backend (MoarVM é o padrão)
rakubrew build moar
rakubrew switch moar
```

#### No Windows:

* Use o instalador disponível em: [https://rakudo.org/downloads](https://rakudo.org/downloads)

---

### ✍️ 2. **Escrevendo seu primeiro script Raku**

Salve um arquivo com a extensão `.raku`, ex:

```raku
# hello.raku
say "Olá, mundo!";
```

Execute:

```bash
raku hello.raku
```

---

### 🔤 3. **Exemplos úteis em Raku**

#### 📌 Variáveis e tipos

```raku
my $nome = "Maria";
my $idade = 30;
say "$nome tem $idade anos";
```

#### 📌 Arrays e loops

```raku
my @nomes = <Ana Bruno Carla>;
for @nomes -> $nome {
    say "Olá, $nome!";
}
```

#### 📌 Expressões regulares poderosas

```raku
my $texto = "O número é 12345";
if $texto ~~ / \d+ / {
    say "Contém número!";
}
```

#### 📌 Orientação a objetos

```raku
class Pessoa {
    has $.nome;
    method saudacao() {
        say "Olá, $.nome!";
    }
}

my $p = Pessoa.new(nome => "Lucas");
$p.saudacao;
```

---

### 💡 Recursos e comunidade

* 📘 [Documentação oficial](https://docs.raku.org)
* 🧪 [Try Raku online](https://glot.io/new/raku)
* 💬 Comunidade: Reddit r/rakulang, Discord, IRC, e StackOverflow

---

## 🧠 Por que aprender Raku?

* É uma linguagem moderna com **sintaxe expressiva**
* Excelente para aprender paradigmas como OO, funcional, concorrente
* Ótima para **explorar regex, DSLs, e metaprogramação**
* Pode ser um diferencial para tarefas que exigem **expressividade e flexibilidade**

---
