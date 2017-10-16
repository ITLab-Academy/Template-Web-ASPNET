# Configurações template Bayer

## Database

Para utilizar o template da Bayer no seu ambiente local será necessário criar dois banco de dados:

* [Banco de dados do seu projeto (e.g. db_Bayer_Xofigo)](DataBase-Version-Control.md)
* Usuarios_Bayer

### Configurando banco de dados Usuarios_Bayer

> Se você estiver utilizando os bancos de dados criados no ambiente da IT Lab esses procedimentos não são necessários

1. Após criar o banco de dados, clique com o botão direito sobre o projeto `Bayer.Usuarios_Bayer.Database` e selecione opção Schema Compare...
1. Na opção Select Target selecione o banco de dados Usuarios_Bayer que você criou
1. Clique no botão `Compare` e em seguida cliente com no botão `Update`
1. Após criar todos os objetos de banco de dados execute diretamente no banco o arquivo `01.dados.sql` do projeto `Bayer.Usuarios_Bayer.Database` na pasta Scripts

> IMPORTANTE: Certifique-se que o usuário que você utiliza para acessar o banco de dados do seu projeto também tenha acesso ao banco Usuarios_Bayer

### Configurando acesso ao banco de dados da aplicação

No projeto `Bayer.Template.Services` abra o arquivo `App.config` e configure a chave de connectionstring para o banco de dados do seu projeto.

No seu projeto API (e.g. Bayer.Xofigo.Api) vá até a pasta Configs e abra o arquivo `ServiceModel.Client.config`. Certifique-se de que o endpoint Bayer.sca.ConnectClient.SCAService está apontando para o serviço local do projeto Bayer.Template.Services (e.g. **localhost:8733**/Bayer.sca.ConnectClient.SCAService) 
