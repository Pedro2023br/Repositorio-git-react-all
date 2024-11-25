
# **Projeto: Aplicativo React com Componente de Menu**

### **Descrição Geral**
Este projeto React tem como objetivo demonstrar a criação de um **componente de menu dinâmico**, que exibe pratos com informações como nome, descrição, preço e imagem. O componente utiliza o **hook `useState`** para gerenciar os dados dos pratos e o **reactstrap** para a estilização.

---

## **Novo Componente Criado: `MenuComponent.js`**

### **Descrição do Componente**
O componente `Menu` é responsável por renderizar uma lista de pratos. Cada prato contém:
- Nome.
- Descrição detalhada.
- Categoria.
- Rótulo (`label`), caso aplicável.
- Preço.
- Imagem.

O componente utiliza o **array de objetos** para representar os pratos, e esses dados são processados dinamicamente para criar a interface exibida ao usuário.

---

### **Bloco 1: Importações**
```javascript
import React, { useState } from 'react'; 
import { Media } from 'reactstrap';
```

- **`React` e `useState`**: Importados para criar o componente funcional e gerenciar o estado local.
- **`Media` do `reactstrap`**: Usado para estruturar a exibição de cada prato com suporte ao estilo do Bootstrap.

---

### **Bloco 2: Definição do Estado**
```javascript
const [dishes] = useState([
    { 
        id: 0, 
        name: 'Uthappizza', 
        image: 'assets/images/uthappizza.png', 
        category: 'mains', 
        label: 'Hot', 
        price: '4.99', 
        description: 'A unique combination of Indian Uthappam (pancake) and Italian pizza, topped with Cerignola olives, ripe vine cherry tomatoes, Vidalia onion, Guntur chillies and Buffalo Paneer.' 
    }, 
    // Outros pratos omitidos para brevidade
]);
```

- **`useState`**: Inicializa o estado local `dishes`, que contém os dados dos pratos.
- **Dados dos pratos**: Cada prato é um objeto com as seguintes propriedades:
  - **`id`**: Identificador único do prato.
  - **`name`**: Nome do prato.
  - **`image`**: Caminho para a imagem associada ao prato.
  - **`category`**: Categoria do prato (ex.: "appetizer", "dessert").
  - **`label`**: Um rótulo opcional (ex.: "Hot", "New").
  - **`price`**: Preço do prato.
  - **`description`**: Texto descritivo.

---

### **Bloco 3: Renderização da Lista de Pratos**
```javascript
const menu = dishes.map((dish) => { 
    return ( 
        <div key={dish.id} className="col-12 mt-5"> 
            <Media tag="li"> 
                <Media left middle> 
                    <Media object src={dish.image} alt={dish.name} /> 
                </Media> 
                <Media body className="ml-5"> 
                    <Media heading>{dish.name}</Media> 
                    <p>{dish.description}</p> 
                </Media> 
            </Media> 
        </div> 
    ); 
});
```

- **`dishes.map`**:
  - Itera sobre o array de pratos para criar um elemento HTML para cada prato.
  - Cada prato é encapsulado em um componente `Media` estilizado.

- **Estrutura do `Media`**:
  - **Imagem**: Renderizada com `Media object`, exibindo o prato.
  - **Cabeçalho**: O nome do prato é destacado com `Media heading`.
  - **Descrição**: Texto explicativo sobre o prato.

---

### **Bloco 4: Estrutura Principal do Componente**
```javascript
return ( 
    <div className="container"> 
        <div className="row"> 
            <Media list> 
                {menu} 
            </Media> 
        </div> 
    </div> 
);
```

- **`<div className="container">`**: Envolve o conteúdo principal para centralizar e aplicar o estilo do Bootstrap.
- **`<div className="row">`**: Define uma linha para os elementos.
- **`<Media list>`**: Agrupa a lista dinâmica de pratos (`menu`), gerada no bloco anterior.

---

### **Bloco 5: Exportação do Componente**
```javascript
export default Menu;
```

- Exporta o componente `Menu`, permitindo que ele seja importado e usado em outros arquivos do projeto (como `App.js`).

---

## **Como o Componente Funciona**
1. Os dados dos pratos são armazenados no estado local (`useState`).
2. Cada prato é processado pelo método `.map()`, que gera um elemento HTML estilizado para exibição.
3. A estrutura gerada é exibida na página, dentro de um layout responsivo fornecido pelo Bootstrap.

---

## **Como Integrar o Componente ao Projeto**
1. No arquivo `App.js`, importe o componente:
   ```javascript
   import Menu from './components/MenuComponent';
   ```
2. Substitua o conteúdo padrão pelo componente `Menu`:
   ```jsx
   function App() {
       return (
           <div className="App">
               <Menu />
           </div>
       );
   }
   ```
3. No arquivo `index.js`, adicione o CSS do Bootstrap:
   ```javascript
   import 'bootstrap/dist/css/bootstrap.min.css';
   ```

---

## **Resultados**
Após realizar as etapas descritas, o projeto exibirá:
- Uma lista dinâmica de pratos com imagens, nomes e descrições.
- Um layout responsivo estilizado com Bootstrap.

Se precisar de ajuda ou informações adicionais, consulte o código ou a estrutura detalhada acima! 😊
