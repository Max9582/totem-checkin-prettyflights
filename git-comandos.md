# Comandos do Git

## 1. Configuração e Inicialização
1. **git config**: Configura variáveis de ambiente do Git (nome, email).
   - `git config --global user.name "Seu Nome"`
   - `git config --global user.email "email@exemplo.com"`
2. **git init**: Inicializa um novo repositório Git local.
   - `git init` (inicializa na pasta atual)
   - `git init meu-projeto` (cria uma pasta já inicializada)
3. **git clone**: Copia um repositório remoto para a máquina local.
   - `git clone https://github.com/usuario/repo.git`
   - `git clone https://github.com/usuario/repo.git pasta-destino`
4. **git remote**: Gerencia conexões com repositórios remotos.
   - `git remote -v` (lista os remotos)
   - `git remote add origin https://url-do-repo.git`

## 2. Operações Básicas
5. **git status**: Mostra o estado da árvore de trabalho (arquivos modificados, staged, etc).
   - `git status`
   - `git status -s` (formato resumido)
6. **git add**: Adiciona arquivos ao staging area (prepara para o commit).
   - `git add index.html` (adiciona um arquivo específico)
   - `git add .` (adiciona todos os arquivos modificados)
7. **git commit**: Salva as mudanças no histórico do repositório.
   - `git commit -m "feat: adiciona login"`
   - `git commit -am "fix: corrige erro de digitação"` (adiciona e commita juntos)
8. **git log**: Exibe o histórico de commits.
   - `git log`
   - `git log --oneline --graph` (visão resumida e gráfica)

## 3. Ramificação (Branches)
9. **git branch**: Lista, cria ou exclui branches.
   - `git branch` (lista branches locais)
   - `git branch feature/nova-tela` (cria uma nova branch)
10. **git checkout**: Muda a branch atual ou restaura arquivos.
    - `git checkout develop` (muda para a branch develop)
    - `git checkout -b bugfix/erro-123` (cria e muda para a branch)
11. **git switch**: Alternativa mais moderna exclusiva para mudar de branches.
    - `git switch main`
    - `git switch -c feature/menu` (cria e muda)
12. **git merge**: Combina o histórico de uma branch com a branch atual.
    - `git merge feature/login` (mescla a feature na branch atual)
    - `git merge --no-ff feature/login` (força a criação de um commit de merge)

## 4. Sincronização e Remoto
13. **git fetch**: Baixa o histórico e as mudanças do remoto, mas não mescla.
    - `git fetch origin`
    - `git fetch --all` (baixa de todos os remotos configurados)
14. **git pull**: Baixa as mudanças do remoto e já mescla na branch atual.
    - `git pull origin main`
    - `git pull --rebase origin main` (faz pull aplicando rebase)
15. **git push**: Envia seus commits locais para o repositório remoto.
    - `git push origin feature/login`
    - `git push -u origin main` (envia e configura o upstream)
16. **git stash**: Guarda temporariamente mudanças não commitadas.
    - `git stash` (guarda as mudanças)
    - `git stash pop` (aplica as mudanças guardadas e as remove do stash)

## 5. Operações Avançadas
17. **git rebase**: Reescreve o histórico aplicando seus commits sobre outra base.
    - `git rebase main` (aplica a branch atual sobre a main)
    - `git rebase -i HEAD~3` (rebase interativo dos últimos 3 commits)
18. **git cherry-pick**: Pega um commit específico de outra branch e aplica na atual.
    - `git cherry-pick a1b2c3d`
    - `git cherry-pick --no-commit a1b2c3d` (aplica as mudanças sem commitar)
19. **git reset**: Desfaz commits movendo o ponteiro da branch.
    - `git reset --soft HEAD~1` (desfaz o commit, mas mantém os arquivos no stage)
    - `git reset --hard HEAD~1` (desfaz o commit e apaga as mudanças nos arquivos)
20. **git revert**: Cria um novo commit que desfaz as mudanças de um commit anterior (seguro para repositórios públicos).
    - `git revert a1b2c3d`
    - `git revert --no-commit a1b2c3d`