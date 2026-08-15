# Saúde 360 — Módulo Gestantes

Este repositório contém o esqueleto inicial do frontend estático para o módulo de gestantes do projeto maior "Saúde Brasil 360".

Avisos e políticas importantes

- "Nunca inserir service_role ou secret keys no frontend."

- Nunca comitar credenciais, chaves administrativas, tokens de serviço ou dados clínicos reais neste repositório.

Dados reais e produção

- Dados reais de pacientes (CPF verdadeiro, dados clínicos, etc.) só poderão ser usados depois que:
  1. A autenticação estiver corretamente implementada e validada;
  2. As Row Level Security (RLS) do Supabase estiverem configuradas e testadas;
  3. Testes de permissão e casos de borda tiverem sido executados e aprovados.

- Durante desenvolvimento use dados fictícios / gerados. Nunca use dados reais em ambientes sem validação completa.

Configuração do frontend

- O frontend pode incluir apenas:
  - SUPABASE_URL (Project URL)
  - SUPABASE_ANON_KEY / publishable key

  Essas chaves são *publicáveis* e só permitem operações permitidas pelas regras de RLS. A service_role key e qualquer secret devem NUNCA ficar no frontend.

Melhores práticas para chaves e build

- Use variáveis de ambiente no processo de build (ex.: `VITE_SUPABASE_URL`, `VITE_SUPABASE_ANON_KEY`) e armazene valores sensíveis em **Secrets** do GitHub Actions, Netlify, Vercel ou no provedor de CI/CD.
- Não adicione arquivos `.env` ao repositório (adicione-os ao `.gitignore`).
- Habilite scanning de segredos (Secret scanning) e branch protections no repositório quando disponível.

Preparação para publicação como site estático

- Branch principal: `main` (padrão deste repositório).
- Para publicar com GitHub Pages: verifique as políticas do seu plano. Alguns planos permitem publicação a partir de repositórios privados; outros exigem repositório público para sites públicos. Não altere a visibilidade automaticamente — verifique o plano e as configurações de Pages antes de publicar.
- Alternativas ao Pages: Netlify, Vercel ou outro host que suporte deploys a partir de repositórios privados ou integrações com CI/CD.

O que este commit inclui

- index.html (placeholder inicial)
- README.md (este arquivo)
- .gitignore (ver abaixo)

Próximos passos sugeridos (manuais)

1. Definir se o repositório deve ser privado: atualmente está configurado como público (veja abaixo). Se desejar, altere a visibilidade em Settings → General → Change repository visibility.
2. Habilitar Secret Scanning e Dependabot (Settings → Security & analysis).
3. Criar e configurar secrets no repositório para deploy e variáveis de build (Settings → Secrets and variables).
4. Instalar / autorizar qualquer GitHub App (ex.: ChatGPT/GitHub App, CI) para ter acesso ao repositório — instruções reduzidas mais abaixo.
5. Validar autenticação e RLS no Supabase antes de importar ou usar qualquer dado real.

Como permitir que um GitHub App ou integração (ex.: ChatGPT/GitHub App) acesse este repositório

- Vá em Settings → Integrations → Installed GitHub Apps (ou Settings → Applications) e instale/conceda acesso ao app para este repositório específico.
- Para apps que usem OAuth ou tokens, pode ser necessário criar um token/PAT com escopos adequados (repo) e fornecê-lo ao app; prefira instalar o GitHub App e conceder acesso apenas ao repositório necessário.
- Para ChatGPT (se estiver usando uma integração baseada em um GitHub App): instale o app e selecione explicitamente `lillykettlin-prog/saude-360-gestantes` durante a instalação.

Observações finais

- Este commit inicial NÃO contém dados sensíveis.
- Garanta que quaisquer chaves ou dados sejam entregues via Secrets e nunca em commits.
