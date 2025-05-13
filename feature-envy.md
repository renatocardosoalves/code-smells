# Feature Envy

## Definição

Feature Envy ocorre quando um método de uma classe depende excessivamente de atributos ou métodos de outra classe para realizar suas operações. Isso pode indicar que o método está "invejando" os dados da outra classe e, provavelmente, deveria ser movido para lá.

---

## Checklist para detecção

- [ ] O método acessa mais atributos/métodos de outra classe do que da própria classe?
- [ ] O método exige muitos parâmetros vindos de outra classe para funcionar corretamente?
- [ ] A lógica do método depende fortemente dos dados de outra classe?
- [ ] É difícil mudar a lógica de outras classes sem impactar este método?
- [ ] Este método usa muitos atributos públicos, getters e setters de outras classes?
- [ ] A lógica deste método poderia ser movida para a outra classe sem impacto negativo?

---

## Soluções Comuns

- **Identificar métodos** que acessam mais dados de outra classe do que da própria.
- Usar o **Move Method** quando possível.
- Usar **Extract Method** para separar lógicas e facilitar o movimento de métodos.
- Seguir o princípio **Tell, Don't Ask** ("ordene, não pergunte").
- Seguir a **Lei de Demeter**.
