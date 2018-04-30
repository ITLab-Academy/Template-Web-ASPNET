# Template Web ASP NET IT Lab
Repositório utilizado para documentar o Template Web ASP NET da IT Lab.
Versão atual do template: **3.2 (30/Abril/2018)** [Release Notes](Release-Notes.md).

# 1ª vez neste repositório?
Clique [Aqui](Welcome.md) e leia as orientações para os iniciantes neste repositório.

# Tecnologias
* **Front-End** (desacoplado do Back-end):
    * HTML 5
    * Javascript
    * AngularJS v1.5.8
    * Bootstrap v3.3.6
    * jQuery v.2.1.4
* **Back-End**:
    * .NET Framework v4.6.2
    * C# 6.0
    * ASP.NET MVC v5.2.3.0
    * Entity Framework v6.0

# Ferramentas para desenvolvimento:
    * Visual Studio 2015 (ou superior) - https://www.visualstudio.com/pt-br/downloads/
    * SQL Server Express 2016 (ou superior) - https://www.microsoft.com/en-us/download/details.aspx?id=54284
    * SQL Server Data Tools (SSDT) - https://docs.microsoft.com/pt-br/sql/ssdt/download-sql-server-data-tools-ssdt
    * NodeJs + NPM - https://nodejs.org/en/

# Problemas conhecidos
Existe uma seção nesta documentação que lista os principais problemas conhecidos que os desenvolvedores passam (ou passaram em versões anteriores) ao realizar o desenvolvimento utilizando o Template Web ASP NET API da IT Lab, caso tenha problemas, verifique se ele já não está com a solução documentada nesta seção, [clicando aqui](known-issues.md).

# Código-fonte do Template Web ASP NET
O código-fonte do Template não fica no GitHub, fica no TFS da IT Lab no endereço abaixo:
    __$/ITLab.TemplateWebApi/Trunk/src__<br>
Sempre utilize a versão da **Branch Trunk**, ela é a última versão estável!

Neste repositório você verá duas pastas, conforme abaixo:
* **ITLabTemplateApi**: Pasta que armazena o código-fonte do template (é este que você vai utilizar para criar novas aplicações).
* **TemplateInspiniaOriginal**: Pasta que armazena o código-fonte original do template HTML do INSPINIA, template este utilizado como base para o template Web ASP NET da IT Lab (você utilizará este apenas como referência para extrair algum componente HTML que ainda não esteja presente no Template Web ASP NET IT Lab). O template Web ASP NET IT Lab foi construído em cima da **versão 2.2 do Template INSPINIA**.

# Setup de um novo projeto
Para criar um novo projeto baseado no template, siga os passos indicados no guia clicando [aqui](Setup-New-Project.md).

# Controle de versão do banco de dados
Para realizar o controle de versão do banco de dados, opte por um dos métodos indicados [aqui](DataBase-Version-Control.md).

# Configuração de rotas e menu
Para configurar as rotas e menu, leia o guia clicando [aqui](Rota-Menu.md).

# Tradução dos termos exibidos pelo sistema
Para criar novos termos e suas traduções e/ou alterar a tradução de termos existentes, leia o guia clicando [aqui](Dictionary.md).

# Cache dos arquivos do Front-End
Por padrão os navegadores realizam o cache dos arquivos de Front-End (HTML/CSS/Javascript), este comportamento pode atrapalhar o desenvolvedor durante o processo de desenvolvimento.
Leia o guia que explica como controlar o cache dos arquivos de Front-End clicando [aqui](FrontEnd-Cache.md).

# Estilo e padrões para codificação - Javascript
Antes de iniciar o desenvolvimento, leia o guia de **Estilo e padrões para codificação - Javascript** clicando [aqui](patterns/Javascript.md), além de se familiarizar com o código pré-existente, sempre siga o mesmo estilo e padrões sugeridos.
