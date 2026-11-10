# MyClient — Portal de operações de TI

Portal responsivo para organizar empresas atendidas, contatos, contratos, acessos remotos e histórico de suporte. A identidade visual usa a logo vetorial `logo-myclients.svg`.

## Recursos

- Cadastro de empresas com dados fiscais, contatos, unidade, contrato, SLA, janela de suporte e observações.
- Inventário por empresa para AnyDesk, VPN, RDP, SSH, TeamViewer e portais web, com identificador, endpoint, login, MFA, responsável, data de verificação e validade.
- Referência ao cofre de senhas para localizar credenciais sem salvar senhas ou códigos MFA no portal.
- Painel com acessos ativos e itens próximos do vencimento; auditoria das ações; exportação CSV dos cadastros de empresas.
- Usuários e permissões individuais para visualizar, cadastrar, editar e excluir clientes e acessos.

## Executar localmente

Na pasta do projeto, execute `python -m http.server 8000` e abra `http://localhost:8000`. No primeiro acesso, crie a conta principal.

Os dados anteriores salvos no mesmo navegador/origem são migrados do armazenamento legado ao abrir a nova versão. O banco IndexedDB persiste no perfil atual do navegador.

## Armazenamento e segurança

Esta versão mantém a base no navegador. Os usuários e registros não são compartilhados entre aparelhos ou perfis diferentes. Para atendimento multiusuário com uma base central, o portal precisa de um backend hospedado com autenticação e banco de dados.

O inventário não deve conter senhas, chaves privadas, códigos de recuperação ou segredos MFA. Use um cofre de credenciais da empresa e preencha somente o caminho/referência desse item. As permissões desta interface organizam o acesso no navegador; não substituem controles de segurança no servidor.

## GitHub Pages

O GitHub Pages publica a interface estática ao selecionar `main` e `/ (root)` em **Settings → Pages**. Ele não executa o backend necessário para compartilhar o banco entre usuários.
