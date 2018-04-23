# Configurações de Rotas e Menu

As rotas e itens do menu são configurados juntos nos arquivos *.js que ficam na pasta **\*.Web\app\routes\\**.
Nesta pasta há um arquivo .js de configuração para cada módulo do sistema (a sepação em arquivos diferentes é apenas para efeito de organização).

O arquivo **core.js** possui a configuração das rotas básicas do sistema, tais como rotas para as páginas de erro e home (página inicial), recomenda-se que evite alterar este arquivo.

Já os demais representam um módulo do sistema e possuem a configuração das rotas e itens do menu do respectivo módulo.

Por exemplo: O arquivo **\*.Web\app\routes\security.js** possui a configuração das rotas e itens do menu relacionados a segurança do sistema.

Abaixo um arquivo típico para configurar as rotas e itens de menu de um determinado módulo:
```javascript
angular
    .module('itlab')
    .config(['$navigationProvider', 'rolesEnum', function (nav, roles) {
        nav.map([
            {
                //Item de menu (é uma rota e é exibido no menu na raiz do menu)
                name: 'home',
                route: '/home',
                title: 'nav.home',
                icon: 'home',
                template: 'app/pages/home/list.html',
                controller: 'homeController',
                bundle: ['app/pages/home/list.controller.js'],                
                nav: 'root',
                order: 0
            },            
            {
                //Item agrupador (pai) de outros itens de menu (não é rota)
                name: 'management',
                title: 'nav.manager',
                icon: 'briefcase',
                nav: 'root',
                order: 1
            },
            {
                //Item de menu filho do item 'management' (é uma rota e é exibido no menu abaixo do item 'management)
                name: 'clients-list',
                title: 'nav.clients',
                route: '/clients',
                template: 'app/pages/clients/list.html',
                controller: 'clientsController',
                bundle: [
                    'app/pages/clients/service.prototype.js',
                    'app/pages/clients/list.controller.js',
                    'app/core/services/form.service.js'
                ],
                nav: 'management',
                order: 1
            },
            {
                //Item é apenas uma rota, não é exibido no menu.
                name: 'clients-edit',
                route: '/clients/:id',
                template: 'app/pages/clients/edit.html',
                controller: 'clientController',
                bundle: [
                    'app/pages/clients/service.prototype.js',
                    'app/pages/clients/edit.controller.js',
                    'app/core/services/form.service.js'
                ]
            }
        ]);
    }]);
```

### Parâmetros e opções

- **name**: Identificador da rota, deve ter um valor único e não pode conter pontos (**.**) e espaço em branco.
- **route**: URL da rota, utilizar a convenção do [ui-router](https://github.com/angular-ui/ui-router/wiki/URL-Routing). (**Nota 1**)
- **title**: Título do item no menu. (**Nota 2**)
- **icon**: Ícone do item do menu, utilizar os sufixos do [font-awesome](http://fontawesome.io/icons/) (ex.: cogs, briefcase). (**Nota 2**)
- **nav**: Indica a posição do item no menu (relação pai x filho), o valor deve ser o mesmo identificador definido na opção *name* ou deve-se definir a palavra 'root' para ser posicionado na raiz do menu. (**Nota 2**)
- **order**: Número que indica a ordem que o item será exibido no menu. (**Nota 2**)
- **template**: URL da página HTML a ser carregada ao acionar a rota. (**Nota 1**)
- **controller**: Nome da controller (AnguarJs) a ser instanciada ao acionar a rota. (**Nota 1**)
- **bundle**: Conjunto de arquivos (urls) a serem carregados *on-demand* ao acionar a rota, como por exemplo arquivos .js e .css. (**Nota 1**)
- **roles**: Array com as roles necessárias para acessar a rota/menu. Caso deseje que qualquer usuário AUTENTICADO tenha acesso a rota, independentemente da sua permissão/perfil, basta deixar o array vazio ou não especificar esta opção. (**Nota 1**)
- **anonymous**: Valor boleano (true/false) que indica se a rota pode ou não ser acessada por um usuário anônimo (não autenticado). Caso não definido o valor padrão é false, ou seja, usuário não autenticado não pode ter acesso. (**Nota 1**)
- **layout**: URL da página mestre a ser carregada. Caso não definido o valor padrão é  'content'). (**Nota 1**)

**Nota 1:**  Caso seja um item agrupador de outros itens de menu, que neste caso não precisa ter rota, esta opção não deve existir na configuração.

**Nota 2:** Caso a rota não deva ser exibida no menu esta opção não deve existir na configuração.

**IMPORTANTE:** Para efeitos de organização, recomanda-se que crie um arquivo .js por módulo do sistema, configurar as rotas e menu de todo o módulo, por exemplo, se você deseja criar um módulo denominado **estoque**, crie um arquivo chamado **estoque.js** na pasta **\*.Web\app\routes\\**, em seguida é necessário referenciar este novo arquivo na página **\*.Web\index.html** na seção **App Rotas Angular**:
```html
    <!-- App Rotas Angular -->
    <script src="app/routes/management.js"></script>
    <script src="app/routes/core.js"></script>
    <script src="app/routes/events.js"></script>
    <script src="app/routes/examples.js"></script>
    <script src="app/routes/health.js"></script>
    <script src="app/routes/security.js"></script>
    <script src="app/routes/settings.js"></script>
```

**Observação:** Ao criar um item para ser exibido no menu, atente-se para o parâmetro **roles**, caso você defina uma role e o usuário ainda não tenha acesso a role definida, o item não será exibido no menu.