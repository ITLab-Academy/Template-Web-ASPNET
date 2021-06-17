# Release Notes

## Versão 4.3 (17/Junho/2021)
- Correção na resposta do back-end para o front-end na API de autenticação (com isso as mensagens amigáveis dos erros não eram exibidas no front-end).
- Exibição de erro amigável quando o usuário não possui o campo Security Stamp definido na tabela (quando se cria usuário direto no banco de dados, prática esta desencorajada!)
- Refatoração da API de autenticação.

## Versão 4.2 (08/Março/2019)
- Nova funcionalidade que permite exportar todos os registros da grid, de todas as páginas (não só os exibidos na primeira página).

## Versão 4.1 (12/Fevereiro/2019)
- Front-End: Forçar usar modo de compatibilidade IE=Edge.
- Front-End: Correção de bug no componente date range picker quando utilizado como seleção de data única e o campo de data esta vazio.
- Front-End / Back-End: Melhoria na gravação das configurações para envio de e-mail (SMTP), validando os dados antes de gravar, evitando dados inconsistentes no banco de dados.
- Front-End / Back-End: Melhoria segurança na exibição das configurações para envio de e-mail (SMTP), evitando retornar do back-end a senha em modo plain-text.

## Versão 4.0 (02/Maio/2018)
- Front-End como WebSite e não mais Projeto (evita gerar /bin no deploy do Front-End).
- Correção na exibição do logo no topo do menu lateral esquerdo.
- Correção no menu para permitir que um item que estiver na raiz/root do menu tenha link direto para rota.

## Versão 3.0 (03/Janeiro/2018)
- Reorganização de pastas e arquivos no projeto Front-End.
- Unificação da configuração de rotas e menu em um único arquivo de configuração (pasta: **\*.Web\app\routes**).
- Implementação de tarefas no [gulp](https://gulpjs.com) para:
   - Levantar o Front-End utilizando um servidor em NodeJs.
   - Criar os arquivos de dicionário .json à partir dos arquivos de dicionário .txt automaticamente, ao levantar o Front-End e ao alterar os arquivos .txt em run-time.
   - Utilizar o [BrowserSync](https://www.browsersync.io/) ao levantar o Front-End, para que, ao alterar qualquer arquivo do Front-End, automaticamente seja dado refresh no navegador.

## Versão 2.2 (28/Dezembro/2017)
- Correção de bug que ocorria ao tentar se autenticar no sistema, no MODO PROTÓTIPO, utilizando o navegador Internet Explorer 11.
- Melhoria na obtenção de dados das APIs utilizando o método GET utilizando o navegador Internet Explorer 11, para instruir o navegador a não realizar cache neste cenário.

## Versão 2.1 (21/Dezembro/2017)
- Correção de bug que ocorria no navegador Safari no iPad/iPhone, referente a palavra-chave 'const' no javascript.