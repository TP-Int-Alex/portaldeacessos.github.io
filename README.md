# Atlas — Portal de gestão

Portal responsivo de clientes, usuários, permissões e atividades. Não requer serviço ou dependências externas para funcionar: utiliza IndexedDB, o banco de dados integrado ao navegador.

## Primeiro acesso

Na pasta do projeto, execute `python -m http.server 8000` e abra `http://localhost:8000`, ou use o endereço HTTPS do site publicado. Crie a conta principal. Se já havia uma conta neste navegador na versão anterior, os dados existentes em `localStorage` são migrados automaticamente para IndexedDB na primeira abertura. Entre com o mesmo e-mail e senha.

Na área **Usuários**, a conta administradora pode criar usuários e configurar individualmente as permissões para visualizar, cadastrar, editar e excluir clientes, consultar usuários e ver o histórico de atividades. A conta principal sempre mantém acesso total.

## Armazenamento local

O banco fica no perfil do navegador e da origem do site. Os dados persistem após fechar e abrir o navegador, mas não são sincronizados entre computadores, navegadores diferentes ou perfis diferentes. Limpar os dados do site no navegador também pode apagar o banco. Para usar uma base compartilhada com várias pessoas em dispositivos distintos, é necessário hospedar um backend com banco central e autenticação; o GitHub Pages, sozinho, hospeda apenas os arquivos estáticos.

As permissões desta versão controlam o que cada usuário vê e faz na interface, mas não substituem as regras de segurança de um servidor para proteger dados compartilhados.

## Publicar a interface

O repositório pode ser publicado no GitHub Pages selecionando `main` e a pasta `/ (root)` em **Settings → Pages**. Isso publica a interface, mas cada navegador continuará com seu próprio banco local.
