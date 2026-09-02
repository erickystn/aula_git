# 🌿 Laboratório Prático de Git & GitHub

![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
![Terminal](https://img.shields.io/badge/CLI-Bash-4EAA25?style=for-the-badge&logo=gnubash&logoColor=white)
![Status](https://img.shields.io/badge/Status-Concluído-brightgreen?style=for-the-badge)
![Licença](https://img.shields.io/badge/Licença-MIT-yellow?style=for-the-badge)

---

## 📖 Visão Geral

O **aula_git** é um repositório laboratório estruturado para a prática e fixação dos fundamentos de controle de versão distribuído utilizando **Git** e **GitHub**. 

Desenvolvido durante a fase introdutória do bootcamp da **Generation Brasil**, o projeto registra na prática o ciclo de vida completo de arquivos (Working Directory, Staging Area e Repositório Local), operações de sincronização com o repositório remoto (Push/Pull), manipulação direta via interface web do GitHub e o uso de estratégias seguras de desfazimento de alterações com `git revert`.

---

## ✨ Competências e Conceitos Praticados

* 📂 **Ciclo de Vida de Arquivos no Git:** Transição de arquivos entre *Untracked*, *Staged* e *Committed*.
* 📝 **Rastreabilidade e Histórico:** Criação de commits semânticos documentando a evolução do projeto.
* ↩️ **Reversão Segura com `git revert`:** Anulação de commits problemáticos sem reescrever o histórico público, preservando a integridade da linha do tempo.
* 🌐 **Sincronização Remota (Local vs Remoto):**
  * Vinculação de repositório remoto (`origin`).
  * Envio de branches e tags (`git push`).
  * Simulação de commits criados diretamente na nuvem (Web UI) e integração com a máquina local via `git pull`.
* 🔀 **Fluxo Básico de Branches:** Trabalho sobre a branch padrão `main` e boas práticas para transição para branches de funcionalidade.

---

## 🎯 Destaques do Histórico Real do Repositório

O histórico de commits deste repositório evidencia exercícios práticos essenciais de engenharia de software:

1. **Commit Inicial (`Primeiro commit`):** Inicialização do repositório e inclusão dos primeiros arquivos de teste.
2. **Ciclo de Reversão (`Segundo commit` e `Revert "Segundo commit"`):** Demonstração do comando `git revert`, gerando um novo commit que desfaz a alteração anterior de forma limpa e auditável.
3. **Simulação de Atualização Concorrente Remota (`Add remote update message to javascript.txt`):** Commit efetuado diretamente na interface do GitHub para simular alterações de outros membros da equipe no repositório compartilhado.
4. **Sincronização e Continuidade (`terceiro commit`):** Pull das alterações remotas para o ambiente local e continuidade do desenvolvimento com a adição de novos módulos (`python.txt`).

---

## 🏗️ Estrutura do Repositório

```text
aula_git/
├── javascript.txt    # Arquivo de prática com alterações locais e remotas
├── python.txt        # Arquivo adicionado para consolidação de novo ciclo de commit
└── README.md         # Documentação e guia prático consolidado de comandos Git
```

---

## 🧭 Guia Prático de Comandos Git

Abaixo está o manual de comandos essenciais praticados neste repositório para consulta rápida:

### 1. Configuração Inicial e Criação
```bash
# Configuração global de identidade (executar apenas na primeira vez)
git config --global user.name "Seu Nome"
git config --global user.email "seu-email@exemplo.com"

# Inicializar um repositório local vazio
git init

# Clonar este repositório para a máquina local
git clone https://github.com/erickystn/aula_git.git
cd aula_git
```

---

### 2. Ciclo Diário de Trabalho
```bash
# Verificar o estado dos arquivos (modificados, staged, untracked)
git status

# Adicionar arquivo específico para a área de preparação (Stage)
git add javascript.txt

# Adicionar todos os arquivos modificados
git add .

# Gravar as alterações no repositório local
git commit -m "feat: adiciona novo arquivo com instruções"
```

---

### 3. Inspeção e Histórico
```bash
# Exibir o histórico completo de commits
git log

# Exibir histórico compacto em uma linha por commit com árvore gráfica
git log --oneline --graph --all
```

---

### 4. Sincronização com o GitHub
```bash
# Vincular repositório local a um repositório remoto
git remote add origin https://github.com/erickystn/aula_git.git

# Enviar commits locais para o branch remoto (com upstream)
git push -u origin main

# Baixar e integrar commits novos da nuvem para o ambiente local
git pull origin main
```

---

### 5. Desfazimento e Reversão Segura
```bash
# Criar um novo commit que desfaz exatamente as mudanças de um commit anterior (Recomendado):
git revert <HASH_DO_COMMIT>

# Descartar alterações de um arquivo que ainda não foi adicionado ao stage:
git restore <nome_do_arquivo>

# Remover um arquivo da área de preparação (unstage):
git restore --staged <nome_do_arquivo>
```

---

## 💻 Diagrama do Fluxo de Trabalho (Git Workflow)

```text
+---------------------+        git add        +------------------+
|  Working Directory  |  ------------------>  |   Staging Area   |
| (Arquivos em edição)|                       | (Área preparada) |
+---------------------+                       +------------------+
          ^                                             |
          |                                             | git commit
          |                 git checkout / restore      v
+---------------------+  <-------------------  +------------------+
|  Repositório Remoto |        git pull        | Repositório Local|
|      (GitHub)       |  ==================>  |    (.git local)  |
+---------------------+  <==================  +------------------+
                               git push
```

---

## 📈 Próximos Passos (Roadmap de Aprendizado)

- [ ] Criação e alternância de branches de funcionalidade (`git checkout -b feature/...`).
- [ ] Mesclagem de branches com `git merge` (Fast-forward e Three-way merge).
- [ ] Simulação e resolução prática de conflitos de merge (*Merge Conflicts*).
- [ ] Uso de `git stash` para salvar alterações temporárias sem commitar.
- [ ] Criação de tags anotadas para versionamento semântico (`git tag -a v1.0.0 -m "Release"`).
- [ ] Automação de pipelines básicos com **GitHub Actions**.

---

## 👤 Autor & 📄 Licença

Desenvolvido por **[Ericky Sant'ana](https://github.com/erickystn)** durante as aulas técnicas da **Generation Brasil**.

Distribuído sob a licença **MIT**.
