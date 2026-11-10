# Atlas — Gestão de clientes

Aplicação web responsiva para cadastro e acompanhamento de clientes locais e internos, usuários, indicadores e atividades.

## Usar

Abra `index.html` em um navegador moderno. No primeiro acesso, crie a conta principal com nome, e-mail e senha de pelo menos 8 caracteres. A conta principal é administradora e pode criar usuários, escolher o perfil (administrador ou equipe) e desativar acessos.

O perfil Equipe pode consultar, cadastrar e editar clientes. O Administrador também pode excluir clientes e gerenciar usuários. Os cadastros podem ser exportados em CSV. O histórico registra ações de login, clientes e usuários.

## Publicar no GitHub Pages

O repositório pode servir esta página estática pela raiz. Ative **Settings → Pages → Deploy from a branch** e escolha a branch principal e a pasta `/ (root)`. Após publicar, o botão **Compartilhar** copia o endereço da página.

## Limite importante do modo atual

Esta versão salva os dados no `localStorage` do navegador. Cada navegador/dispositivo terá seus próprios cadastros, usuários e registros; criar usuários dentro do portal não cria contas compartilhadas na internet. O login local serve para organização e não substitui autenticação de servidor. Antes de usar com dados reais ou compartilhar uma base entre pessoas, conecte um backend com autenticação e banco de dados (por exemplo, Supabase ou Firebase), aplique regras de acesso no servidor e migre o armazenamento. O GitHub Pages, sozinho, não oferece esse backend.
