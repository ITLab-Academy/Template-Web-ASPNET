# Trabalhando com o dicionário de termos e suas traduções
## Introdução
O template utiliza o i18n para realizar a tradução dos termos, com isso, temos um dicionário com os termos que são apresentados na aplicação.

**IMPORTANTE:** Este mecanismo não é para realizar a tradução dos __dados transacionais incluídos no banco de dados__, ele é para realizar a tradução somente dos termos fixos exibidos no sistema, como por exemplo labels.

No projeto **.Web** na pasta **locales** temos:
- As pastas que representam a sigla do idioma, como por exemplo: **en** (inglês), **es** (espanhol) e **pt-br** (português). Estas pastas armazenam os arquivos .json que contém os termos e a tradução conforme o idioma da pasta em que o arquivo estiver.

  **IMPORTANTE:** Não é recomendado que os arquivos destas pastas sejam alterados diretamente, o indicado é que estes arquivos sejam gerados automaticamente à partir de um script *.js* que será explicado mais abaixo.

- Os arquivos .txt que contém, por linha, o termo e todas as traduções do termo, separados por pipes ( **|** ). São estes arquivos que devem ser alterados caso se deseje incluir novos termos e/ou alterar a tradução de termos existentes.

## Como funciona
Nos arquivos **.html**, no elemento em que você deseja exibir um texto traduzido, você deve incluir a tag **ng-i18n** e o valor desta tag deve ser o código do termo, este código deve ser único para toda a aplicação, pode ser criado livremente por você e recomenda-se que ele refira-se ao termo que se deseja tradução. 

**Exemplo:** Imagine que você queira criar um novo label para exibir o texto "Telefone" na tela, no **html** você deve criar:
```html 
<label ng-i18n="label.telefone"></label>
```
Em seguida você deve criar no dicionário o termo e suas traduções, no arquivo *general-app.txt* cria-se o termo **label => telefone | Phone | Telefone | Teléfono**, sendo que:
- **label => telefone**: É o código do termo, o mesmo utilizado no html no formato ``label.telefone``.
- **| Phone | Telefone | Teléfono**: São as traduções dos termos, no idioma inglês, português e espanhol respectivamente.

  **Observação:** A ordem das traduções, separadas por pipes ( | ), deve ser aquela indicada na 1ª linha do   arquivo .txt, que por padrão está configurado como: `i18n=> | en | pt-BR | es`, ou seja, inglês | portuguê | espanhol.

Caso o termo indicado no arquivo .html não exista no dicionário (arquivo .txt / .json), ao executar o sistema será exibido o código do termo, no exemplo acima, será exibido **label.telefone** ao usuário.

Porém, o arquivo .txt não é o arquivo utilizado pelo sistema para exibir os termos traduzidos, este arquivo é utilizado apenas para o desenvolvedor gerenciar de uma melhor forma as traduções dos termos.
É necessário gerar os arquivos .json com as traduções, são estes os arquivos utilizados pelo ssistema para exibir os termos traduzidos ao usuário.

## Gerando os arquivos .json com as traduções.
Uma vez criado o arquivo .txt, basta gerar os arquivos .json para cada idioma, utilizando um script javascript.
Para gerar os arquivos .json você precisa atender os requisitos abaixo:
- Que você tenha o **NodeJs** e **NPM** instalados em seu computador.
- Que os pacotes do node, responsáveis por criar os arquivos .json à partir dos arquivos .txt, estejam instalados. Para instalar estes pacotes siga os passos abaixo:
  1. Vá até o prompt de comando.
  2. Navegue até a raiz da pasta que armazena o projeto **.Web** (pasta em que se encontra o arquivo **package.json**).
  3. Execute o comando:
  ```bash
  npm install
  ```
- Que já existam as pastas que vão armazenar os arquivos .json por idioma dentro da pasta **locales**.
- Que você realize o check-out de TODAS as pastas que armazenam .json.

Tendo os pré-requisitos acima atendidos, siga os passo abaixo:
1. Abra o prompt de comando.
2. Navegue até a pasta **nodeScripts** que está no projeto **.Web**.
3. Execute o arquivo **i18nGenerator.js** através do comando: 
```bash
node i18nGenerator.js
```
Este script irá gerar os arquivos .json nas pastas conforme o idioma.

## Arquivos envolvidos nas traduções
O template está preparado para ler os seguintes arquivos para exibir os termos traduzidos (este conjunto de arquivos ficam dentro das pastas por idioma):
- alerts-app.json
- alerts.json
- datatables.json
- general-app.json
- general.json

Para cada arquivo .json acima existe um arquivo .txt:
- **alerts-app.txt**: Este arquivo contém os termos e traduções das mensagens de alertas que são exibidos aos usuários do sistema. Caso você deseja incluir/alterar um termo que seja um alerta a ser exibido ao usuário, é este arquivo que você deve manipular.
- **alerts.txt**: Este arquivo, assim com o arquivo acima, contém os termos e traduções das mensagens de alertas que são exibidos aos usuários do sistema, porém, **deve-se evitar manipular este arquivo**.
- **datatables.txt**: Este arquivo contém os termos e traduções das mensagens exibidas nas grids (datatables), **deve-se evitar manipular este arquivo**.
- **general-app.txt**: Este arquivo contém os termos e traduções das mensagens gerais que são exibidos aos usuários do sistema. Caso você deseja incluir/alterar um termo ao usuário que não seja um alerta, é este arquivo que você deve manipular.
- **general.txt**: Este arquivo, assim com o arquivo acima, contém os termos e traduções das mensagens gerais que são exibidos aos usuários do sistema, porém, **deve-se evitar manipular este arquivo**.

**ATENÇÃO:** Os arquivos que NÃO contém o sufixo **-app** em seu nome são os arquivos que contém os termos e traduções base e essenciais para a maioria das funções do sistema, recomenda-se que estes arquivos não sejam manipulados, caso deseje incluir e/ou alterar termos, manipule os arquivos que contém o sufixo **-app** em seu nome.



