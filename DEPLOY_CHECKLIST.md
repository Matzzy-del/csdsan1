# Checklist rápido — Supabase + Vercel

## Supabase

- [ ] Criar um projeto no Supabase
- [ ] Abrir SQL Editor
- [ ] Executar `supabase/schema.sql`
- [ ] Confirmar que Authentication > Providers > Email está ativo
- [ ] Copiar Project URL
- [ ] Copiar Publishable key

## GitHub

- [ ] Criar um repositório novo
- [ ] Enviar todos os arquivos desta pasta, exceto `node_modules`

## Vercel

- [ ] Add New > Project
- [ ] Importar o repositório
- [ ] Framework: Vite
- [ ] Adicionar `VITE_SUPABASE_URL`
- [ ] Adicionar `VITE_SUPABASE_PUBLISHABLE_KEY`
- [ ] Deploy

## Após o deploy

- [ ] Copiar a URL final da Vercel
- [ ] Supabase > Authentication > URL Configuration
- [ ] Site URL: URL final da Vercel
- [ ] Redirect URLs: adicionar a URL final da Vercel
- [ ] Criar uma conta no NEXO
- [ ] Confirmar o e-mail, caso a confirmação esteja ativa
- [ ] Fazer o primeiro login
- [ ] Conferir se a tabela `user_app_state` recebeu uma linha
