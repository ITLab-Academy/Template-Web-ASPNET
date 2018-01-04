# Release Notes

## Versão 3.0 (03/Janeiro/2018)
- Reorganização de pastas e arquivos no projeto Front-End.
- Unificação da configuração de rotas e menu em um único arquivo de configuração (pasta: **\*.Web\app\routes**).
- Implementação de tarefas no [gulp](https://gulpjs.com) para:
   - Levantar o Front-End utilizando um servidor em NodeJs.
   - Criar os arquivos de dicionário .json à partir dos arquivos de dicionário .txt automáticamente, ao levantar o Front-End e ao alterar os arquivos .txt em run-time.
   - Utilizar o [BrowserSync](https://www.browsersync.io/) ao levantar o Front-End, para que, ao alterar qualquer arquivo do Front-End, automaticamente seja dado refresh no navegador.

## Versão 2.2 (28/Dezembro/2017)
- Correção de bug que ocorria ao tentar se autenticar no sistema, no MODO PROTÓTIPO, utilizando o navegador Internet Explorer 11.
- Melhoria na obtenção de dados das APIs utilizando o método GET utilizando o navegador Internet Explorer 11, para instruir o navegador a não realizar cache neste cenário.

## Versão 2.1 (21/Dezembro/2017)
- Correção de bug que ocorria no navegador Safari no iPad/iPhone, referente a palavra-chave 'const'.