# God Class

## Definição

Uma God Class é um *code smell* que ocorre quando uma única classe assume muitas responsabilidades dentro do sistema. Ela centraliza diversas funcionalidades que deveriam estar distribuídas entre diferentes classes menores e especializadas.

Ela se torna uma "classe Deus", acumulando tantas funcionalidades que se torna difícil de entender, manter e testar. Isso viola diretamente o Princípio da Responsabilidade Única (SRP), um dos princípios SOLID, tornando o código difícil de manter, testar e modificar.

---

## Checklist para detecção

- [ ] A classe tem muitas funções não relacionadas entre si?
- [ ] Há métodos que poderiam pertencer a outras classes mais específicas?
- [ ] O arquivo da classe tem centenas (ou milhares) de linhas de código?
- [ ] A classe tem muitos métodos públicos?
- [ ] A classe possui uma quantidade excessiva de atributos?
- [ ] Outras classes dependem fortemente dessa classe para realizar suas operações?
- [ ] Pequenas mudanças nessa classe impactam diversas partes do sistema?
- [ ] A classe importa muitas outras classes ou módulos não relacionados?
- [ ] O código dessa classe mantém muitas instâncias de outras classes?
- [ ] Testar a classe exige configurar um grande número de dependências?

---

## Soluções Comuns

- **Revisão do encapsulamento** de classes que estão deixando suas responsabilidades vazarem para a God Class. Após identificar esses vazamentos, mover o código para sua respectiva classe.
- **Aplicar o Single Responsibility Principle (SRP)** para dividir responsabilidades.
- **Identificar responsabilidades** que a God Class está assumindo e extraí-las para classes especializadas.
- **Reorganizar os métodos** de acordo com seus contextos pode facilitar a identificação das responsabilidades da God Class.
- **Aplicar Design Patterns** como:
  - `Facade`
  - `Strategy`
  - `Command`

Esses padrões podem ajudar a extrair responsabilidades da God Class e auxiliar no processo de refatoração.
