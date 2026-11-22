# ITACHI BOT PRO — Vercel + CyberHost HTTP

Esta versão **não bloqueia o formulário** quando `ITACHI_API_URL` é `/backend`.

## Instalação
1. Extrai os ficheiros e coloca **index.html**, **admin.html**, **config.js** e **vercel.json** na raiz do repositório GitHub.
2. Aguarda um novo deploy **Ready** na Vercel.
3. Verifica se o rodapé do login apresenta **22NOV-HTTP3**.
4. Usa o botão **Verificar ligação ao servidor (sem PIN)**.
5. Se receberes 401/403, o proxy provavelmente alcançou a API; se receberes 404/502/HTML, anota o código e revê o rewrite/rota.

## Arquitectura
A Vercel recebe `/backend/api/...` e redirecciona para `http://node.cyberhost.site:3023/api/...`. O servidor CyberHost **não é alterado**.

## Risco importante
A perna **Vercel → CyberHost usa HTTP não encriptado**. Não é seguro introduzir PINs de contas reais ou processar dados financeiros sensíveis enquanto essa perna permanecer em HTTP. A remoção do bloqueio elimina apenas a barreira no frontend; **não corrige a confidencialidade** nem garante a conectividade real. Também é necessário confirmar que a API não concede permissões de executor a logins web.
