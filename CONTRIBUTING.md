Contribuindo para o repositório — Saúde 360 — Módulo Gestantes

Obrigado por contribuir. Antes de enviar PRs, leia as regras abaixo para manter segurança e privacidade.

1. Política de commits e PRs
   - Faça alterações em branches com nomes descritivos: `feature/`, `fix/`, `chore/`.
   - Crie Pull Requests direcionados à `main` e descreva claramente as mudanças.
   - Evite force-push na branch `main`.

2. Segurança e dados sensíveis
   - NUNCA comite chaves secretas, service_role keys, tokens administrativos, senhas ou dados de pacientes reais.
   - Use dados falsos para desenvolvimento e testes locais.
   - Se encontrar uma chave acidentalmente comprometida, comunique imediatamente e rotacione a credencial.

3. Variáveis de ambiente e secrets
   - Armazene secrets em Settings → Secrets and variables (GitHub) e nunca em arquivos versionados.
   - Para builds locais, utilize arquivos `.env` listados no `.gitignore`.

4. Testes e validação antes de usar dados reais
   - Não importe dados reais até que autenticação e RLS no Supabase estejam implementadas e validadas.
   - Forneça testes de permissão e revise casos de borda.

5. CI/CD
   - Este repositório inclui um workflow de CI básico que realiza uma varredura por padrões comuns de segredos.
   - Configure deploys em CI apenas após adicionar secrets e revisar permissões.

6. Como permitir integrações (ex.: ChatGPT/GitHub App)
   - Instale o GitHub App e conceda acesso ao repositório `lillykettlin-prog/saude-360-gestantes`.
   - Prefira concessão de acesso por repositório (não global) e utilize o menor conjunto de permissões necessárias.

Agradecemos por manter a privacidade e a segurança dos dados enquanto desenvolvemos este módulo.
