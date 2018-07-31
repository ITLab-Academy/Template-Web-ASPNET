# Cache dos arquivos Front-End

Por padrão os navegadores realizam o cache dos arquivos de Front-End (HTML/CSS/Javascript), este comportamento pode atrapalhar o desenvolvedor durante o processo de desenvolvimento, onde o navegador poderá não exibir mudanças realizadas nestes arquivos.

Você pode controlar este comportamento de três formas:
1. Utilizando o controle de cache do navegador.
2. Utilizando o controle de cache do template.
3. Abrindo o navegador em modo anônimo.

## 1. Controle de cache no navegador
Esta é a forma mais eficiente para o desenvolvedor controlar se os arquivos do Front-End deverão ou não serem carregados do cache.
No navegador **Google Chrome** abra a janela **Ferramentas do desenvolvedor**, pressionando **F12** ou acionando o menu **Mais Ferramentas** >> **Ferramentas do desenvolvedor**.
Com a janela **Ferramentas do desenvolvedor** aberta, vá até a guia **Network**, nesta guia você verá a opção **Disable Cache**. Quando esta opção ESTÁ ATIVA o navegador não carrega os arquivos do cache, quando esta opção NÃO ESTÁ ATIVA o navegador tenta carregar os arquivos do cache.

 <img src="images/Chrome-Disable-Cache.png">

**IMPORTANTE**: A opção de não carregar os arquivos do cache só funciona se a opção **Disable Cache** estiver ativa e a janela **Ferramentas do desenvolvedor** e guia **Network** estiver aberta ao mesmo tempo em que você acessar o sistema (carregar os arquivos).

## 2. Controle de cache do template
O template traz um mecanismo que permite você controlar se deseja ou não carregar os arquivos do cache, este mecanismo funciona para a maioria dos arquivos de Front-End, mas não todos, conforme detalhes abaixo:

### Arquivos no qual este mecanismo funciona:
- Arquivos carregados pelo componente **ocLazyLoad**, ou seja, aqueles configurados no arquivo **/app/app.route.js** e arquivos **\*.route.js** que estiverem na pasta **/app/routes** do projeto **\*.Web**.
- Arquivos carregados pelo AngularJs (exemplo: arquivos de templates).

Por padrão o template já vem configurado para não carregar os arquivos de Front-End do cache, você pode controlar este comportamente alterando o valor da variável **cacheFrontEndFiles** que está presente no arquivo **/app/core/config/app.config.js**.
```javascript
cacheFrontEndFiles: false
```
Quando o valor desta variável é igual a **true**, o navegador é quem controlará se os arquivos devem ou não serem carregados do cache.

Quando o valor desta variável é igual a **false**, o navegador não carregará os arquivos do cache, isso porque este mecanismo incrementa um time stamp no nome do arquivo, "enganando" o navegador que identificará que é uma URL ainda não acessada e portanto não carregará o arquivo do cache.

Exemplo da chamada do arquivo através deste mecanismo quando o a variável **cacheFrontEndFiles: false**:
```bash
http://localhost:8080/app/core/pages/security/login/login.html?_dc=1508175624339
```
Onde **_dc=1508175624339** é o time stamp injetado pelo mecanismo do template para "enganar" o navegador.

**IMPORTANTE**: Ao implantar o sistema no ambiente de produção é recomendável que esta variável esteja configurada como **cacheFrontEndFiles: true**, para deixar o navegador controlar se os arquivos devem ou não serem carregados do cache, isso melhorará a performance do sistema no dia-a-dia.


### Arquivos no qual este mecanismo NÃO FUNCIONA:
- Arquivos referênciados diretamente nos arquivos .HTML, como por exemplo os arquivos referênciados no arquivo **index.html**:
```html
<script src="app/app.routes.js"></script>
```
Para estes casos você deve manualmente alterar a referência ao arquivo incluindo um tipo de time stamp ou versão, como no exemplo abaixo, ou até mesmo utilizar o controle de cache do navegador como explicado mais acima.
```html
<script src="app/app.routes.js?v2"></script>
```

## 3. Navegador modo anônimo
Outra forma eficiente de evitar que o navegador carregue os arquivos Front-End do cache é abrir o navegador em modo anônimo, ao abrir o navegador neste modo o cache existente é ignorado ao carregador os arquivos, com isso um novo contexto de cache é criado pelo navegador para a sessão atual aberta em modo anônimo.
Ao alterar os arquivos, **caso o navegador já esteja aberto em modo anônimo**, como ele criou um novo contexto de cache guardando neste contexto os arquivos abertos pela última vez, para evitar que o cache seja carregado você deve fechar e abrir novamente o navegador em modo anônimo.

