# Trabalhando com o dicionário de termos e suas traduções
## Introdução
O template utiliza o i18n para realizar a tradução dos termos, com isso, temos um dicionário para cada idioma com os termos que são apresentados na aplicação.

**IMPORTANTE:** Este mecanismo não é utilizado para realizar a tradução dos __dados transacionais incluídos no banco de dados__, ele é utilizado para realizar a tradução somente dos termos fixos exibidos no sistema, como por exemplo labels.

No projeto **.Web** na pasta **\public\locales** temos as pastas que representam a sigla do idioma, como por exemplo: **en** (inglês), **es** (espanhol) e **pt-br** (português). Estas pastas armazenam os arquivos .json que contém os termos e a tradução conforme o idioma da pasta em que o arquivo se encontra.

  **IMPORTANTE:** Não é recomendado que os arquivos destas pastas sejam alterados diretamente/manualmente, o indicado é que estes arquivos sejam gerados automaticamente através de uma tarefa do <strong>gulp</strong>, que será explicado mais abaixo.

No projeto **.Web** na pasta **\assets\locales** temos os arquivos .txt que contém, por linha, o termo e todas as traduções do termo separados por pipes ( **|** ). São estes arquivos que devem ser alterados caso se deseje incluir novos termos e/ou alterar a tradução de termos existentes.

## Como funciona
Nos arquivos **.html**, no elemento em que você deseja exibir um texto traduzido, você deve incluir a tag **ng-i18n** e o valor desta tag deve ser o código do termo, este código deve ser único para toda a aplicação, pode ser criado livremente por você e recomenda-se que ele refira-se ao termo que se deseja tradução. 

**Exemplo:** Imagine que você queira criar um novo label para exibir o texto "Telefone" na tela, no **html** você deve criar:
```html 
<label ng-i18n="label.telefone"></label>
```
Em seguida você deve criar no dicionário (arquivo .txt) o termo e suas traduções, no arquivo *general-app.txt* cria-se o termo **label => telefone | Phone | Telefone | Teléfono**, sendo que:
- **label => telefone**: É o código do termo, o mesmo utilizado no html no formato ``label.telefone``.
- **| Phone | Telefone | Teléfono**: São as traduções dos termos, no idioma inglês, português e espanhol respectivamente.

  **Observação:** A ordem das traduções, separadas por pipes ( | ), deve ser aquela indicada na 1ª linha do   arquivo .txt, que por padrão está configurado como: `i18n=> | en | pt-BR | es`, ou seja, inglês | portuguê | espanhol.

Caso o termo indicado no arquivo .html não exista no dicionário (arquivo .txt ou .json), ao executar o sistema será exibido o código do termo, no exemplo acima, será exibido **label.telefone** ao usuário.

Porém, o arquivo .txt não é o arquivo utilizado pelo sistema para exibir os termos traduzidos, este arquivo é utilizado apenas para o desenvolvedor gerenciar de uma melhor forma as traduções dos termos.
É necessário gerar os arquivos .json com as traduções, são estes os arquivos utilizados pelo ssistema para exibir os termos traduzidos ao usuário.

## Gerando os arquivos .json com as traduções.
Caso você esteja executando o Front-End através do <strong>NodeJs + gulp</strong> ([saiba mais aqui](Setup-New-Project.md), seção <strong>Executando os projetos Back-End e Front-End</strong>), ao alterar o arquivo do dicionário .txt e salvar, automaticamente o gulp detectará que o arquivo foi alterado e irá gerar o arquivo dicionário .json, ou seja, neste caso basta alterar o arquivo do dicionário .txt e salvar. O gulp também gera os arquivos do dicionário .json automaticamente à partir dos arquivos do dicionário .txt sempre que se levanta o projeto Front-End através do comando gulp.

Caso você esteja executando o Front-End através do Visual Studio, na linha de comando execute o comando abaixo estando na pasta do projeto Front-End (**\*.Web\\**):
```
gulp translate
```
Este comando irá gerar os arquivos do dicionário .json à partir dos arquivos do dicionário .txt.

<strong>IMPORTANTE:</strong> Para executar o gulp é necessário que você tenha instalado:
1. **NPM + NodeJs**, conforme indicado [aqui](README.md) na seção <strong>Ferramentas para desenvolvimento</strong>.
2. **gulp** no modo global e **Pacotes do NPM** utilizados no Front-End, conforme indicado [aqui](Setup-New-Project.md) na seção <strong>Instalando e restaurando os pacotes do Front-End com o NPM</strong>.

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



