# Crie-um-Gerenciador-de-Esferas-do-Dragon-BallZ-Usando-ReactJS-Jest-React-Testing-Library-e-Cypress

Vamos criar um projeto chamado **Gerenciador de Esferas do Dragon BallZ**. Este projeto será uma aplicação web desenvolvida com ReactJS e incluirá testes com Jest, React Testing Library e Cypress para garantir a qualidade do software.

### Descrição do Projeto:
O objetivo é construir uma aplicação que permita aos usuários gerenciar as sete Esferas do Dragão. Quando todas as esferas estiverem reunidas, o usuário poderá "invocar" o Shenlong e fazer um desejo (simulado na aplicação).

### Funcionalidades:
- **Listar Esferas**: Exibir todas as esferas do dragão disponíveis.
- **Adicionar/Remover Esfera**: Permitir que o usuário adicione ou remova esferas da lista.
- **Verificar Esferas**: Checar se todas as sete esferas foram coletadas.
- **Invocar Shenlong**: Se todas as esferas estiverem coletadas, permitir que o usuário invoque o Shenlong.

### Módulos:
1. **Esfera**: Componente React para representar cada esfera do dragão.
2. **Lista de Esferas**: Componente para listar todas as esferas.
3. **Gerenciador de Esferas**: Lógica para adicionar/remover esferas e verificar a coleção.
4. **Shenlong**: Componente para simular a invocação do Shenlong.

### Testes:
- **Jest**: Para testes unitários dos componentes e lógica de negócios.
- **React Testing Library**: Para testes de integração e garantir que os componentes funcionem como esperado.
- **Cypress**: Para testes end-to-end e simular o comportamento do usuário na aplicação.

Aqui está um exemplo de como você pode estruturar o componente `Esfera` em React:

```jsx
import React from 'react';

function Esfera({ numero, adicionarEsfera, removerEsfera }) {
  return (
    <div>
      <h2>Esfera do Dragão {numero}</h2>
      <button onClick={() => adicionarEsfera(numero)}>Adicionar</button>
      <button onClick={() => removerEsfera(numero)}>Remover</button>
    </div>
  );
}

export default Esfera;
```

E um exemplo de teste usando Jest para este componente:

```javascript
import { render, fireEvent } from '@testing-library/react';
import Esfera from './Esfera';

test('permite ao usuário adicionar e remover uma esfera', () => {
  const adicionarEsfera = jest.fn();
  const removerEsfera = jest.fn();
  const { getByText } = render(<Esfera numero={1} adicionarEsfera={adicionarEsfera} removerEsfera={removerEsfera} />);

  fireEvent.click(getByText('Adicionar'));
  expect(adicionarEsfera).toHaveBeenCalledWith(1);

  fireEvent.click(getByText('Remover'));
  expect(removerEsfera).toHaveBeenCalledWith(1);
});
```

Esses são apenas exemplos básicos para começar. Você precisará expandir e modularizar o código para incluir todas as funcionalidades e testes necessários.
