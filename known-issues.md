# Lista dos problemas conhecidos ao realizar o desenvolvimento com o Template Web ASP NET API
## Abertura da Solução/Projeto
1. Ao abrir a solução tenho a mensagem de erro abaixo: (SQL Server Express)
<br><img src="images/error-sql-server-express-missing.png">

<strong>Sintoma:</strong> Falta do SQL Server Express 2016 na máquina do desenvolvedor.
<strong>Solução:</strong> Instale o SQL Server Express 2016 (ou superior) https://www.microsoft.com/en-us/download/details.aspx?id=54284

2. Ao abrir a solução, tenho a mensagem de erro abaixo: (SSDT)
<br><img src="images/error-ssdt-missing.png">

<strong>Sintoma:</strong> Falta do SSDT (SQL Server Data Tools) na máquina do desenvolvedor.
<strong>Solução:</strong> Instale o SSDT na máquina do desenvolvedor. https://docs.microsoft.com/pt-br/sql/ssdt/download-sql-server-data-tools-ssdt

3. Após abrir a solução, um ou mais projetos ficam marcados com o erro <strong>(load failed)</strong> ao lado do nome da solução e com isso o projeto não abre.
<strong>Sintoma:</strong> Falta do SSDT (SQL Server Data Tools) e/ou SQL Server Express 2016.
<strong>Solução:</strong> Instale o SSDTe SQL Server Express 2016 na máquina do desenvolvedor. 
