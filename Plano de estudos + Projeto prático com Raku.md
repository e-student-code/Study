Vamos montar um **plano de estudos + projeto prático em Raku**, ideal para você que quer aprender a linguagem enquanto faz algo útil, como **automação de tarefas ou parsing de logs**.

---

## 🎯 Objetivo do Projeto:

Criar um **script em Raku** que:

1. **Lê um arquivo de log** (ex: `access.log`)
2. **Filtra linhas com base em padrões (como IPs ou códigos de erro)**
3. **Conta e exibe estatísticas simples**
4. **Gera um relatório resumido**

---

## 📚 Plano de Estudos Raku — Focado em Automação & Parsing

### 🧩 Etapa 1 — Fundamentos Raku (1–2 dias)

| Tópico            | Conteúdo                         | Comando                       |
| ----------------- | -------------------------------- | ----------------------------- |
| Sintaxe básica    | `say`, `my`, `if`, `for`, `sub`  | `say "Olá, mundo"`            |
| Tipos de dados    | Strings, Números, Arrays, Hashes | `my @arr = <um dois três>`    |
| Loops e condições | `for`, `while`, `when`, `if`     | `for 1..5 -> $i { say $i }`   |
| Regex básico      | `/\d+/`, captura de grupos       | `if $line ~~ /(\d+)/ { ... }` |

👉 **Prática:** Crie um script que leia um arquivo linha a linha e imprima as linhas que contêm números.

---

### 🧩 Etapa 2 — Manipulação de Arquivos (1 dia)

| Tópico              | Conteúdo                     | Exemplo                                |
| ------------------- | ---------------------------- | -------------------------------------- |
| Leitura de arquivos | `slurp`, `lines`, `IO::Path` | `for "log.txt".IO.lines -> $l { ... }` |
| Escrita de arquivos | `spurt`, `append`            | `spurt "out.txt", $texto`              |

👉 **Prática:** Leia um arquivo `.log` e salve todas as linhas que contêm “ERROR” em outro arquivo.

---

### 🧩 Etapa 3 — Regex Avançado (2 dias)

| Tópico                          | Exemplo                     |           |
| ------------------------------- | --------------------------- | --------- |
| Captura de grupos nomeados      | `/<ip=(\d+)>/`              |           |
| Combinação de múltiplos padrões | \`if \$line \~\~ / '404'    | '403' /\` |
| Substituição                    | `$line ~~ s/ERROR/WARNING/` |           |

👉 **Prática:** Extraia endereços IP e códigos HTTP de um log de acesso web (tipo Apache).

---

### 🧩 Etapa 4 — Estruturação de Dados (1 dia)

| Tópico                  | Exemplo                  |
| ----------------------- | ------------------------ |
| Hashes para contagem    | `my %ips; %ips{$ip}++`   |
| Agrupamento e ordenação | `sort`, `Bag`, `Hash`    |
| Geração de relatório    | `say "$ip => $contagem"` |

👉 **Prática:** Conte quantas vezes cada IP aparece no log.

---

## 🛠️ Estrutura do Projeto: `log-analyzer.raku`

### 📄 Exemplo de log (`access.log`)

```
192.168.0.1 - - [12/May/2025:10:32:16] "GET /index.html" 200
192.168.0.2 - - [12/May/2025:10:35:12] "POST /login" 403
192.168.0.1 - - [12/May/2025:10:36:45] "GET /admin" 404
```

### ⚙️ Objetivos do script:

* Filtrar linhas com erros (403, 404)
* Contar ocorrências por IP
* Salvar relatório

### 🧪 Código base:

```raku
my %ips;
for "access.log".IO.lines -> $line {
    if $line ~~ / ^ (\d+ '.' \d+ '.' \d+ '.' \d+) .* (\d\d\d) $ / {
        my $ip = ~$0;
        my $status = ~$1;
        if $status ~~ / 403 | 404 / {
            %ips{$ip}++;
        }
    }
}

spurt "relatorio.txt", "IPs com erros 403/404:\n";
for %ips.kv -> $ip, $count {
    spurt "relatorio.txt", "$ip => $count\n", :append;
}
```

---

## 📦 Extras se quiser aprofundar:

* 📈 Gerar gráficos com Raku (usando módulos como `SVG::Plot`)
* 🌐 Enviar relatório por email ou webhook
* 🐚 Integrar com cron jobs (automação real)

---

## ✅ Checklist de Habilidades Aprendidas

* [ ] Leitura e escrita de arquivos
* [ ] Uso de regex avançado
* [ ] Contagem e estruturação de dados com hashes
* [ ] Escrita de scripts automatizados
* [ ] Manipulação de texto e logs

