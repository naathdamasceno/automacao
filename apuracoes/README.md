# Apurações · Planning

Gera os arquivos de importação (Domínio TXT / Winthor XLSX) de ICMS e PIS/COFINS a partir dos livros fiscais em PDF e dos resumos em Excel.

- **Página:** GitHub Pages (`index.html`, arquivo único, sem build).
- **Dados e login:** Supabase, projeto `apuracoes` (região São Paulo).
  - `usuarios`: cadastro de quem acessa (perfil, admin, pode editar). Alterado só pela função `admin-usuarios`.
  - `empresas`: cadastro, filiais e mapeamento de contas (`dados` em JSON) e histórico de alterações.
  - `exclusoes`: registro de empresas excluídas.
- **Segurança:** todas as tabelas com RLS. Só usuários cadastrados leem; só quem tem `pode_editar` (ou admin) grava empresas. Autor e horário de cada alteração são carimbados pelo banco.

A chave que aparece no `index.html` é a chave **publicável** do Supabase. Ela é pública por definição; quem protege os dados são as regras de RLS.
