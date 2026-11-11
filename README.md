# MyClient — Portal de operações de TI

Portal de suporte para registrar empresas atendidas, acessos, chamados, equipamentos, licenças e atividades da equipe. Usa uma logo vetorial própria e interface responsiva.

## Módulos

- **Empresas:** dados fiscais, contatos, unidades, contratos, SLA e janela de suporte.
- **Acessos:** inventário AnyDesk, VPN, RDP, SSH, TeamViewer e portais, com identificador, host, login, MFA, responsável e datas de validade/revisão.
- **Chamados:** categoria, prioridade, prazo, responsável, status e descrição/solução.
- **Equipamentos:** tipo, patrimônio, série, hostname, IP, sistema, local, responsável e garantia.
- **Licenças:** fornecedor, modalidade, quantidade de assentos e renovação.
- **Assistente:** busca local por linguagem natural nos dados liberados para o perfil e sugestões de triagem.
- **Relatórios:** workbook `.xlsx` com abas por módulo e relatório imprimível para salvar em PDF.
- **Usuários e auditoria:** permissões granulares e histórico das ações.

## Permissões

A conta principal tem acesso administrativo total e pode escolher, para cada usuário, quais módulos pode consultar e quais registros pode cadastrar, editar ou excluir. Usuários com perfil administrativo delegado continuam limitados às permissões marcadas pela conta principal.

## Executar localmente

Na pasta do projeto, execute `python -m http.server 8000` e abra `http://localhost:8000`. Crie a conta principal no primeiro acesso. O banco IndexedDB persiste no perfil deste navegador. Cadastros antigos no armazenamento local migram automaticamente quando a nova versão é aberta na mesma origem.

## Busca e relatórios

A busca inteligente roda localmente no navegador; nenhuma informação é enviada a um modelo ou serviço externo. O PDF abre a janela de impressão do navegador para escolher **Salvar como PDF**. O Excel é um arquivo `.xlsx` gerado localmente e inclui apenas os módulos permitidos ao usuário atual.

## Segurança e hospedagem

O inventário guarda referências a um cofre de credenciais, não senhas, códigos de recuperação, chaves privadas ou segredos MFA. As permissões desta interface organizam o acesso no navegador e não substituem autorização no servidor.

Os dados ficam no navegador e não são sincronizados entre aparelhos. O GitHub Pages publica apenas a interface estática. Para usuários remotos compartilharem a mesma base com segurança, é necessário hospedar um backend com autenticação e banco de dados central.
