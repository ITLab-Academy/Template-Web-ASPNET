# Setup de um novo projeto baseado no Template Web ASP NET IT Lab
Passos:
1. Através do Source Control do Visual Studio, navegue até a pasta **$/ITLab.TemplateWebApi/Trunk/src/**.

2. Dê um *Get Lastet Version* na pasta **ITLabTemplateAPI**
    <br>Com isso o Visual Studio irá baixar uma cópia do template na pasta mapeada em sua máquina.
    <br>**IMPORTANTE:** A pasta a ser mapeada no Visual Studio para baixar o código-fonte do template não pode ser **C:\TEMP**, caso seja esta pasta você terá problemas nos passos seguintes.
    <br>**ATENÇÃO:** Não utilize este código-fonte recém baixado na sua máquina para desenvolver o novo projeto, você deverá seguir os passos abaixo que ajudará a criar uma cópia deste código-fonte já preparado para o seu novo projeto.

3. Abra um *Prompt de Comando* do Windows e navegue até a pasta onde o código-fonte do template foi baixado.

4. Execute o comando **SetupSolution.exe**.
    <br>Ao executar este comando iniciará um pequeno wizard para te auxiliar na criação, a 1ª pergunta será o nome do seu novo projeto, defina o nome do seu novo projeto evitando espaços e caracteres especiais.
    <br>Ao término da execução deste wizard, uma cópia do código-fonte do template será criada na pasta **C:\TEMP\** em uma subpasta com o nome que você definiu no wizard.

