## Respostas do Desafio

**1. Por que a Secret aparece no log como `***` e a variável aparece normalmente?**
As *secrets* são informações sensíveis (como tokens, senhas, chaves de API) e o GitHub aplica automaticamente um mecanismo de segurança que mascara esses valores nos logs, substituindo-os por `***`. Isso evita vazamento de dados confidenciais.
Já as *variables* (vars) não são consideradas sensíveis, por isso seus valores são exibidos normalmente no log.

---

**2. O job `deploy_app` consegue ler a variável `BUILD_VERSION` criada no job `build_app`? Por quê?**
Não. Cada job no GitHub Actions é executado em um ambiente isolado (runner diferente). As variáveis definidas em um job não são automaticamente compartilhadas com outros jobs.
Para compartilhar dados entre jobs, seria necessário usar outputs ou outras estratégias específicas, como artifacts ou variáveis de ambiente persistidas manualmente.
