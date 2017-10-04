# Configurações de Rotas e Menu

## Rotas

Para configurar uma nova rota basta editar o arquivo `app.route.js` na pasta app.

Primeiramente é necessário que você configure o módulo da rota, esse módulo será a base de acesso as páginas que você criar.

Ex.:

Caso você tenha criado uma série de páginas referentes a produtos tais como:

* edit.html
* list.html
* gallery.html

O seu módulo pode se chamar `products` e pode ser configurado conforme abaixo:

```javascript
...

.state('products', {
    resolve: {
        authorize: ['authorization', function (authorization) { return authorization.authorize(); }]
    },
    url: '/products',
    templateUrl: 'app/core/layout/content.html'
})

...

```

Uma vez o módulo das rotas configurado basta configurar as páginas conforme abaixo:

```javascript
...

.state('products.list', {
    url: '/edit',
    templateUrl: 'app/pages/products/list.html',
    controller: 'productListController',
    controllerAs: 'viewModel',
    resolve: {
        deps: ['$ocLazyLoad', function ($ocLazyLoad) {
            return $ocLazyLoad.load({
                name: 'itlab',
                insertBefore: '#ng_load_plugins_before', // load the above css files before a LINK element with this ID. Dynamic CSS files must be loaded between core and theme css files
                files: ['app/pages/products/list.controller.js']
            });
        }]
    },
    data: { pageTitle: 'List Products', roles: [] }
})

.state('products.edit', {
    url: '/edit',
    templateUrl: 'app/pages/products/edit.html',
    controller: 'productEditController',
    controllerAs: 'viewModel',
    resolve: {
        deps: ['$ocLazyLoad', function ($ocLazyLoad) {
            return $ocLazyLoad.load({
                name: 'itlab',
                insertBefore: '#ng_load_plugins_before', // load the above css files before a LINK element with this ID. Dynamic CSS files must be loaded between core and theme css files
                files: ['app/pages/products/edit.controller.js']
            });
        }]
    },
    data: { pageTitle: 'Edit Product', roles: [] }
})

.state('products.gallery', {
    url: '/edit',
    templateUrl: 'app/pages/products/gallery.html',
    controller: 'productGalleryController',
    controllerAs: 'viewModel',
    resolve: {
        deps: ['$ocLazyLoad', function ($ocLazyLoad) {
            return $ocLazyLoad.load({
                name: 'itlab',
                insertBefore: '#ng_load_plugins_before', // load the above css files before a LINK element with this ID. Dynamic CSS files must be loaded between core and theme css files
                files: ['app/pages/products/gallery.controller.js']
            });
        }]
    },
    data: { pageTitle: 'Edit Product', roles: [] }
})

...

```

## Menu

Para adicionar suas páginas no menu basta editar o arquivo `sideMenu.config.js` na pasta app > core > config.

Abaixo um exemplo de como ficaria configurado para as páginas de products citadas na configuração das rotas:

```javascript
...

{
    description: 'Products',
    icon: 'briefcase',
    submenu: [
        {
            description: 'List',
            toState: 'products.list'
        },
        {
            description: 'Gallery',
            toState: 'products.gallery'
        }
    ]
},

...

```