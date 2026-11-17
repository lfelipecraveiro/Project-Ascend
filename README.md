# 🚀 Project Ascend

Aplicação pessoal de produtividade e disciplina gamificada, inspirada em Trello, Habitica e RPGs. Uso individual, sem login, sem servidor e sem banco de dados remoto: tudo roda no navegador e os dados ficam no `localStorage` do próprio dispositivo.

## Funcionalidades
- **Painel:** XP, nível, moedas, sequência de dias, taxa de conclusão, Índice de Consistência (ponderado por prioridade), gráfico de XP dos últimos 7 dias, próximas tarefas e conquistas.
- **Quadros (kanban):** múltiplos quadros, listas editáveis, arrastar e soltar (e seletor "mover" para celular), edição completa de cartões (título, descrição, prioridade, complexidade, prazo), histórico de alterações e confirmação antes de excluir.
- **Hábitos** com sequência e últimas 14 datas; **checklists pontuados** com bônus de conclusão.
- **Recompensas** (loja de moedas) e **consequências leves** para atrasos, com limite diário e sem punições retroativas.
- **Livro-razão de transações:** toda mudança de XP/moedas é uma transação com id e chave única. Cada conclusão rende recompensa uma única vez, e editar ou excluir cartões nunca altera o saldo. Há limite diário de XP vindo de tarefas contra abuso. A tela **Configurações → Auditoria** confere saldo × histórico.
- **Backup:** exportação/importação em JSON versionado (formato v2), com migração, validação e confirmação.

## Tecnologias
HTML, CSS e JavaScript puros em um único `index.html` (código organizado em módulos lógicos por comentários). Sem dependências, sem build, sem servidor.

## Executar localmente
Abra o `index.html` no navegador. Alternativamente: `python3 -m http.server 8000` e acesse `http://localhost:8000`.

## Backup e restauração
Os dados ficam no navegador e no domínio em que o app foi aberto. Limpar os dados do site, trocar de navegador ou de dispositivo significa começar do zero, então faça backups com regularidade.
- **Exportar:** em **Configurações → Backup**, copie o texto JSON e guarde em um arquivo seu (por exemplo `ascend-backup.json`, que o `.gitignore` já ignora).
- **Restaurar:** cole o JSON na caixa e clique em **Importar backup**. O app valida o arquivo, mostra um resumo e pede confirmação antes de substituir os dados atuais. Backups de versões antigas são migrados automaticamente; backups de versão mais nova são recusados.
- **Cópia local:** cada importação guarda os dados anteriores em uma cópia local. Use **Salvar cópia local agora** e **Recuperar última cópia local** para voltar atrás. Essa cópia fica no mesmo navegador e não substitui o backup em arquivo.

## Licença
MIT. Veja `LICENSE`.
