# Refused Bequest

## Definição

Refused Bequest acontece quando uma subclasse herda métodos e atributos de sua superclasse, mas não os utiliza, ignora seu contrato ou viola suas expectativas.  
Isso indica que a herança está sendo mal utilizada, criando uma relação entre classes que não faz sentido conceitual.  
O famoso "é-um" (*is-a*) acaba sendo forçado.

---

## Checklist para detecção

- [ ] A subclasse herda métodos que nunca são utilizados no código?
- [ ] Métodos herdados são sobrescritos apenas para lançar exceções?
- [ ] A subclasse redefine métodos herdados apenas para evitar comportamentos da superclasse?
- [ ] Há métodos na superclasse que não fazem sentido para todas as subclasses?
- [ ] A herança está sendo usada apenas como forma de reutilizar código (sem relação semântica real)?
- [ ] O nome da superclasse sugere um conceito que não se aplica diretamente à subclasse?
- [ ] Há subclasses que não podem ser tratadas como instâncias da superclasse sem causar problemas lógicos?

---

## Soluções Comuns

- Avaliar se a herança está sendo usada apenas para reutilização de código.  
  Se sim, considerar **substituir por composição**.

- Verificar se a subclasse **realmente representa o conceito da superclasse**.  
  Se não, **remover a herança** e buscar outra modelagem.

- Criar **subclasses mais específicas** ou **interfaces segmentadas**, herdando apenas o necessário.  
  Exemplo: dividir uma superclasse `Ave` em `AveVoadora` e `AveNaoVoadora`.

- Refatorar a superclasse para que seus métodos sejam **genéricos e aplicáveis** a todas as subclasses.

- Separar comportamentos distintos em **classes auxiliares** e usá-las por composição.  
  Exemplo: mover lógica de voo para uma classe `ComportamentoDeVoo`.

- Usar o **Princípio da Segregação de Interfaces (ISP)** para evitar superclasses ou interfaces com métodos irrelevantes.

- **Evitar sobrescrever métodos herdados apenas para lançar exceção** ou anular o comportamento original.

- Garantir que a **substituição da superclasse pela subclasse** não quebre o funcionamento esperado do código.  
  Isso ajuda a manter o **Princípio de Liskov**.
