# Lista dos problemas conhecidos ao realizar o desenvolvimento com o Template Web ASP NET API
## Abertura da Solução/Projeto
<strong>1. Ao abrir a solução tenho a mensagem de erro abaixo: (SQL Server Express)</strong>
<br><img src="images/error-sql-server-express-missing.png">

<strong>Causa:</strong> Falta do SQL Server Express 2016 na máquina do desenvolvedor.
<br><strong>Solução:</strong> Instale o SQL Server Express 2016 (ou superior) https://www.microsoft.com/en-us/download/details.aspx?id=54284

<br><br>
<strong>2. Ao abrir a solução, tenho a mensagem de erro abaixo: (SSDT)</strong>
<br><img src="images/error-ssdt-missing.png">

<strong>Causa:</strong> Falta do SSDT (SQL Server Data Tools) na máquina do desenvolvedor.
<br><strong>Solução:</strong> Instale o SSDT na máquina do desenvolvedor. https://docs.microsoft.com/pt-br/sql/ssdt/download-sql-server-data-tools-ssdt

<br><br>
<strong>3. Após abrir a solução, um ou mais projetos ficam marcados com o erro <strong>(load failed)</strong> ao lado do nome da solução e com isso o projeto não abre.</strong>
<br><strong>Causa:</strong> Falta do SSDT (SQL Server Data Tools) e/ou SQL Server Express 2016.
<br><strong>Solução:</strong> Instale o SSDTe SQL Server Express 2016 na máquina do desenvolvedor.

## Execução do sistema em browser Safari no iPad/iPhone
<strong>4. Problemas ao executar o sistema no browser Safari no iPad/iPhone</strong>

<strong>Sintoma:</strong> Ao executar o sistema no browser Safari no iPad/iPhone o sistema não executa corretamente, podendo apresentar a mensagem abaixo no lugar das mensagens provindas do dicionário (ex: labels):
```html
{{translation()}}
``` 
<p>Além disso, ao debugar, a mensagem de erro abaixo é exibida no console do Developer Tools do navegador:</p>

```html
SyntaxError: Unexpected keyword 'const'. Const declarations are not supported in strict mode. 
```
<strong>Causa:</strong> Utilização da keyword 'const' no Javascript em strict mode.
<br><strong>Solução:</strong> Não utilize a keyword 'const', utilize 'var'
<br><strong>IMPORTANTE:</strong> O Template Web da IT Lab à partir da versão 2.1 já não utiliza mais a keyword 'const' no Javascript, as versões anteriores do template podem apresentar este problema, neste caso basta aplicar a solução descrita acima.
