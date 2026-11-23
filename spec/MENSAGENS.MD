# especificação do módulo de mensagens da rede social brasil

Objetivo: criar uma aplicação de mensagens brasileira similar ao Whatsapp.

Contexto: Atualmente no mundo há uma grande discussão sobre controle de dados pessoais e o poder das big techs no mundo, com base nessas discussões foi idealizado o Brasil, um projeto que visa criar um software com diferentes redes sociais. Em vista, o primeiro módulo será o de mensagens, similiar ao whatsapp. 

Importante:

## Stack

Objetivo: frontend totalmente separado do backend

Frontend Web: PHP, HTML5, CSS e JavaScript (todos vanilla, sem frameworks)
- Todo o código fonte deve ser criado dentro de um diretório chamado 'web' na raiz do projeto
- Iniciar via terminal no ambiente de desenvolvimento

Backend: PHP puro, sem frameworks
- Todo o código fonte deve ser criado dentro de um diretório chamado 'backend' na raiz do projeto
- Iniciar via terminal no ambiente de desenvolvimento

Banco de dados: MySql
- Instalar localmente via docker

Segredos em variáveis de ambiente compartilhadas tanto pelo frontend como pelo backend: arquivo .env na raiz do projeto

### Estrutura de diretórios

- web/: frontend web
- backend/: backend
- docs/: documetação 
- sql/: schema e migrations mysql
- spec/: especificações do projeto
- assets/: imagens, vídeos e elementos gráficos
- css/: css de cada página e um root de cores, fontes de textos e ícones

Importante: em docs, devem ser criadas documentações técnicas e sobre o sistema, incluindo como rodar cada parte no ambiente de desenvolvimento e também para deploy em produção. É interessante ter um README geral, outro para o frontend e outro para o backend. Também ter um CHANGELOG. Cada linha de código do backend deve conter uma explicação de cada funcionalidade. 

## Login

No login, o sistema exibe o padrão de autenticação inspirado no Gov.br, organizado em um layout dividido em duas colunas sobre um fundo claro com detalhes geométricos sutis nas cores nacionais (verde, amarelo e azul).

### Cabeçalho e Rodapé

O topo apresenta o logotipo e o nome Brasil Chat à esquerda. No rodapé da tela, ficam os links institucionais (Termos de Uso, Privacidade e Acessibilidade) à esquerda e a versão do sistema à direita.

#### Área Institucional (Coluna Esquerda)

Exibe uma mensagem de boas-vindas com tipografia em destaque ("Conversas que aproximam pessoas."), subtítulo explicativo sobre a proposta da plataforma e uma linha decorativa segmentada nas cores da identidade visual.

#### Card de Autenticação (Coluna Direita)

•  Centraliza um formulário branco com bordas arredondadas que simula o acesso único do gov.br. Ele contém a marca gov.br, o título "Entre no Brasil Chat", um campo de entrada para o CPF, um botão principal em verde ("Entrar com Gov.br"), um link de suporte ("Está com problemas para entrar?") e um aviso informativo destacando que se trata apenas de uma simulação visual sem integração oficial.

## Regras gerais para o design

cor principal: #009739
cor secundário(destaque): #FFDF00 
cor terciária: #002776

fonte principal: Inter 

### Layout desktop

O modelo de layout desktop é estruturado no formato grid, dividido em uma sidebar estreita de navegação global à esquerda, um painel lateral de lista de conversas no centro-esquerda e uma área principal de chat à direita — sendo que tanto a lista quanto a conversa possuem seus próprios cabeçalhos fixos e áreas de rolagem independentes.

#### Sidebar de Navegação

Estruturalização: Barra vertical fixa em verde-escuro com ícones de acesso rápido às seções do sistema (chats, contatos, grupos, status, chamadas e salvos), além de configurações e perfil do usuário na base.

cor de fundo: #042F1B

Funcionalidades: 

1. Ao clicar na logo, sistema exibe tela inicial com um icone no meio, um titulo(slogan) e uma paragrafo auxiliar.
2. Ao clicar no ícone de chat, sistema exibe painel lateral de lista de conversas.
3. Ao clicar no ícone de contatos, sistema exibe lista completa de todos os contatos do usuários.
4. Ao clicar no ícone de grupos, sistema exibe painel lateral de lista de grupos.
5. Ao clicar no ícone de status, sistena exibe status do usuário, juntamente da opção de adicionar novo status. Sistema também exibe listagem com todos os contatos que compartilharam status.
6. Ao clicar no ícone de chamadas, sistema exibe lista completa de todas as chamadas realziadas do usuário.
7. Ao clicar no ícone de favoritos, sistema exibe tudo que foi marcado como favorito pelo usuário.
8. Ao clicar no ícone de configuração, sistema exibe: informações sobre o perfil do usuário com a opção de editar perfil, notificações(modal no estilo checklist para ativar determinadas notificações do sistema), privaciade e segurança(modal com bloqueios e visibilidades), conversas(modal com a possibilidade de alterar papel de parede e baixar histórico completo de mensagens), tema escuro, Acessibilidade(modal com funcionalidades para  pessoas com deficiência), ajuda e suporte(modal com número do sistema e opção de baixar os termos). Botão de sair do sistema.
9. Ao clicar no ícone de perfil, sistema exibe modal com as informações(Nome, telefone e recado) do usuário e sua foto de perfl, sendo possível alterar apenas o recado e a foto, já que no usuário entrar com as credenciais do govbr(nome e telefone).



Regras lógicas: 

1. Caso não exista conversas, sistema apresenta mensagem informando que não há conversas.
2. Caso não exista contatos, sistema exibe botão com modal de adicionar novo contato.
3. Caso não exista grupos, sistema exibe botão com modal de criar novo grupo com listagem de contatos do usuário.
4. Caso não exista status do usuário, sistena não exibe status do usuário.
5. Caso não exista status do contato do usuário, sistema informa sobre.
6. Caso não o usuário não possua chamadas realizadas, sistema informa sobre.
7. Caso não o usuário não possua itens favoritados, sistema informa sobre.
8. Caso o usuário já esteja com o sistema no tema escuro, sistema troca por tema claro.
9. Caso não o usuário não possua  recado, sistema informa sobre.

##### Painel de Conversas

Composta por um cabeçalho superior com a logo, área de busca com atalho e filtros em pílula (Todas, Não lidas, Favoritas, Grupos), uma lista rolável de contatos com avatares e contadores de notificação, e um rodapé fixo para conversas arquivadas.

##### Área Útil de Conversa (Coluna Principal)

Estruturada com um cabeçalho superior contendo os dados do contato ativo e botões de ação (busca e chamadas), uma área central rolável em cinza claro com os balões de mensagem (alinhados à direita para enviadas em verde-claro e à esquerda para recebidas em branco) e uma barra inferior fixa para digitação, emojis e anexos.

### Layout mobile

O modelo de layout responsivo mobile adapta a estrutura de múltiplas colunas para uma exibição em tela única, composta por um cabeçalho superior fixo, uma área útil central rolável e uma barra de navegação inferior.

#### Cabeçalho Superior

Fixado no topo da tela, apresenta o logotipo e o título "Brasil Chat" à esquerda e o ícone de adição (+) para iniciar novas conversas à direita (com o entalhe/ilha dinâmica do dispositivo centralizado no topo).

#### Área Útil Principal

Ocupa a porção central com rolagem vertical e reúne a barra de pesquisa (ex: Pesquisar conversas), os botões de filtro rápido em formato de pílula (ex: Todas, Não lidas, Favoritas e Grupos), a lista vertical de contatos e grupos (com avatares coloridos, prévias de mensagens, horários e badges verdes de notificações) e o acesso às conversas Arquivadas na base da lista.



## Contatos

1. 

## Chat

Regras lógica:

1. 

### Botão de envio

Regras:

1. Se não tiver texto, mostrar ícone de microfone
2. Se tiver texto, mostrar ícone de envio

#### Design do botão

- cor principal #009739
- mouse em cima: cor secund

### Design

1. Seção de digitação da mensagem na parte inferior da tela
2. Botão para anexar imagens,..
3. Campo de texto com informação digite sua mensagem aqui
4. Botão com ícone de microfone ou de envio dependendo da situação