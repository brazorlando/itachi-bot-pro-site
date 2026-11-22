# ITACHI BOT PRO — Correcção da ligação (22NOV-C2)

Substitui NA RAIZ do repositório GitHub os ficheiros `index.html`, `admin.html`, `config.js` e `vercel.json`. Aguarda o deploy **Ready** no Vercel.

No site, a mensagem **Versão de ligação: 22NOV-C2** confirma que o código novo foi publicado. Carrega em **Verificar ligação ao servidor (sem PIN)**. Envia apenas o resultado desse teste.

Um HTTP 401/403 ao consultar /backend/api/v4/dashboard sem token indica que o backend provavelmente foi alcançado e recusou acesso anónimo (esperado). 404/502/HTML dão pistas diferentes de configuração e conectividade.

**Segurança:** o backend actual usa HTTP. Por isso, login/registo com PIN ficam bloqueados nesta versão de diagnóstico. É necessário configurar TLS HTTPS no acesso do servidor V5 antes de autenticação ou pagamentos reais. O admin está protegido, mas as rotas /api/owner/* ainda não foram construídas.
