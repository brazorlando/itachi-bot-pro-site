# ITACHI BOT PRO — Portal Comercial

Site HTML/CSS/JS pronto para alojamento estático na Vercel. O servidor Node.js V5 e o executor Android **não** pertencem a este repositório.

## Publicar
1. Crie um repositório GitHub (preferencialmente privado).
2. Envie `index.html`, `config.js`, `vercel.json` para a raiz do repositório.
3. Entre em https://vercel.com/new, importe o repositório.
4. **Framework Preset**: Other; **Root Directory**: `./`; **Build Command**: vazio; **Output Directory**: `.` ou padrão (sem pasta `public`).
5. Clique **Deploy**. O site abre em `https://<projecto>.vercel.app`.

## Ligar ao servidor V5
Em `config.js`, substitua a string vazia pelo endereço HTTPS **real** da API:

```js
window.ITACHI_API_URL = "https://api.seu-dominio.com";
```

O backend tem de permitir **CORS** para o domínio HTTPS do portal e o cabeçalho `Authorization`, ou deve configurar um proxy de mesma origem via Vercel para um backend também HTTPS. **Não use o antigo endereço HTTP da CyberHost para logins reais**. Enquanto a API não estiver em HTTPS, a interface pode ser publicada, mas os dados, login e pagamentos não devem ser usados em produção.

**Segurança adicional obrigatória antes da produção:** separar credenciais de comerciante web das credenciais do executor APK, revisar protecção contra tentativas de PIN, autorizações por tenant e integrar pagamento verificado pelo backend. Esta versão não constitui validação de produção.

## Dados
Os indicadores são consultados da API. Em caso de falha, aparece uma mensagem legível; o portal não substitui dados reais por resultados fictícios.
