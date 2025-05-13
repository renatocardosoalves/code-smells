# Inconsistent State

## Definição

No contexto de Orientação a Objetos, o *Code Smell* "Inconsistent State" ocorre quando objetos são criados ou configurados sem atender a todos os requisitos para seu estado ser válido.

---

## Checklist para detecção

- [ ] O construtor permite criar um objeto sem inicializar todos os atributos necessários?
- [ ] Métodos setters permitem definir valores inválidos para atributos?
- [ ] Existe um fluxo onde métodos podem ser chamados na ordem errada, deixando o objeto inconsistente?
- [ ] Há variáveis booleanas que indicam "modos" do objeto, tornando seu comportamento imprevisível?
- [ ] O estado de um atributo depende de outro, mas isso não é garantido automaticamente?
- [ ] Há muitos `if` verificando se o objeto está em um estado correto antes de chamar um método?
- [ ] Métodos frequentemente precisam "consertar" o estado do objeto antes de operar?

---

## Soluções Comuns

- Use **construtores ricos**, exigindo todos os dados obrigatórios no momento da criação do objeto.  
  Se necessário, use o padrão **Factory** para objetos mais complexos mantendo a consistência.

- Evite **setters públicos**. Prefira métodos que encapsulem a intenção, como `alterarPreco()` em vez de `setPreco()`.  
  Sempre valide os dados e rejeite valores inválidos com exceções.

- Modele o objeto com **estados explícitos** ou **máquinas de estado**.  
  Controle transições com validações internas.  
  O padrão **State** pode ajudar a representar essas transições.

- Substitua múltiplos **booleanos** por uma única propriedade que represente o estado atual.  
  Para maior robustez, use **enum** ou constantes bem definidas.

- Centralize a modificação de atributos interdependentes em métodos únicos.  
  **Encapsule a lógica de dependência**, sem expor atributos diretamente.

- Encapsule comportamentos e valide o estado **internamente**, reduzindo duplicações, evitando erros e melhorando a coesão.  
  *(Evita o Feature Envy)*.
