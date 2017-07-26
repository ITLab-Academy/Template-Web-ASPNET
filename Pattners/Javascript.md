# Javascript:

**Nomenclatura dos arquivos:**
  - O template possui dois modos: **Protótipo (Prototype)** e **Desenvolvimento**, no modo Protótipo o **Front-End** fica desacoplado do **Back-End**, com isso temos uma agilidade maior na criação do protótipo onde todas as operações de persistência (inserir/alterar/excluir) são realizadas em memória, simulando a persistência, sem acionar as APIs do **Back-End** (e consequentemente sem acionar banco de dados).
   - Basicamente os arquivos de serviços do AngularJs são os que possuem as duas versões: **Protótipo** e **Desenvolvimento**. Os arquivos de protótipo terminam com o nome `.prototype.js`, já os arquivos de desenvolvimento não possuem nenhuma indicação especial. Exemplo: 
      - O arquivo `service.prototype.js` indica que é um arquivo utilizado apenas em **tempo de protótipo** (simula a persistência em memória, não aciona o Back-End).
      - O arquivo `service.js` indica que é um arquivo utilizado em **tempo de desenvolvimento** (aciona as APIs do Back-End).

**Estilo e convenções de codificação:**
  - **Nome de Variáveis e Funções:** Utilizar o padrão **camelCase** (1ª letra maiúscula da 1ª palavra minúscula e iniciais das demais palavras maiúscula) e sempre iniciando com letras, exemplo: `firstName`   (não utilizar utilizar ~~`FirstName`~~ / ~~`Firstname`~~ / ~~`firstname`~~ / ~~`3firstName`~~).
  - **Espaço entre os operadores:** Sempre utilizar espaços entre os operadores, exemplo `var soma = x + y;`  (não utilizar ~~`var soma = x+y;`~~.
  - **Sentenças Simples:** (como: objeto)
    - **Ponto-e-vírgula:** Sempre concluir as sentenças SIMPLES com ponto-e-vírgula, exemplo `var colors = ['Red', 'Blue'];`.
    - **Propriedade/Valor:** Utilizar o dois-pontos (:) colado ao nome da propriedade e inserir um espaço entre o dois-pontos (:) e o valor.
  - **Sentenças Complexas:**  (como: Funções / Loop / Condicionais)
    - **Ponto-e-vírgula:** Nunca concluir as sentenças COMPLEXAS com ponto-e-vírgula, exemplo:

```javascript
function toCelsius(fahrenheit) {
    return (5 / 9) * (fahrenheit - 32);
}; //Evitar este último ponto-e-vírgula
```
  - **Sentenças Simples e Complexas:**
    - **Sentenças compostas:**
      - Colocar abertura de chaves no final da 1ª linha: `{`.
      - Inserir um espaço em branco antes das chaves: `var person = {`.
      - Colocar fechamento de chaves em uma nova linha.

**Exemplos sugeridos:**

_**Objeto:**_
```javascript
var person = {
    firstName: 'John',
    lastName: 'Doe',
    age: 50,
    eyeColor: 'blue'
};
```

_**Funções:**_
```javascript
function toCelsius(fahrenheit) {
    return (5 / 9) * (fahrenheit - 32);
}
```
_**Loops:**_
```javascript
for (i = 0; i < 5; i++) {
    x += i;
}
```
_**Condicionais:**_
```javascript
if (time < 20) {
    greeting = "Good day";
} else {
    greeting = "Good evening";
}
```