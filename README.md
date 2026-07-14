# NEXO V4 Cloud — Vercel + Supabase

Versão pronta para deploy na Vercel com login e sincronização no Supabase.

## Estrutura técnica

- Vite
- Supabase Auth por e-mail e senha
- tabela `user_app_state` com um documento JSON por usuário
- Row Level Security: cada usuário acessa somente os próprios dados
- armazenamento local como fallback offline
- sincronização automática com debounce
- migração automática dos dados locais no primeiro login

## 1. Criar o projeto no Supabase

1. Crie um projeto.
2. Abra **SQL Editor**.
3. Execute todo o arquivo `supabase/schema.sql`.
4. Abra **Authentication > Providers > Email** e mantenha e-mail/senha ativo.
5. Em **Authentication > URL Configuration**, depois do deploy, use a URL da Vercel como Site URL e Redirect URL.

## 2. Variáveis

Copie `.env.example` para `.env.local` e preencha:

```env
VITE_SUPABASE_URL=https://SEU-PROJETO.supabase.co
VITE_SUPABASE_PUBLISHABLE_KEY=SUA_CHAVE_PUBLICA
```

Use somente a chave pública/publishable. Nunca use `service_role` no frontend.

## 3. Rodar localmente

```bash
npm install
npm run dev
```

## 4. Publicar na Vercel

1. Envie esta pasta para um repositório GitHub.
2. Na Vercel, clique em **Add New > Project** e importe o repositório.
3. Framework Preset: **Vite**.
4. Adicione as duas variáveis em **Settings > Environment Variables**.
5. Faça o deploy.
6. Volte ao Supabase e configure a URL final em Authentication > URL Configuration.

## Banco

O app usa uma linha JSONB por usuário. Para este aplicativo pessoal, isso reduz bugs e mantém todas as funções existentes. Caso o sistema vire um SaaS grande, o banco deve ser normalizado em tabelas separadas.
