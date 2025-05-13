# Shotgun Surgery

## Definição

O *Shotgun Surgery* ocorre quando uma única modificação em um sistema exige mudanças em diversos lugares. Isso dificulta a manutenção, aumenta o risco de erros e reduz a clareza do código. Esse problema geralmente indica a falta de **coesão**, onde as responsabilidades relacionadas estão espalhadas por múltiplas classes ou funções.

---

## Checklist para detecção

- [ ] Alterar uma regra de negócio exige mudanças em múltiplos lugares?
- [ ] Um mesmo conceito ou lógica de negócio está repetido em diversas classes?
- [ ] Um bug gera impacto em diversas classes?
- [ ] Classes diferentes precisam se modificar juntas?
- [ ] Há muitas classes acessando diretamente os mesmos dados?
- [ ] Testes unitários frequentemente falham em massa quando há uma pequena modificação?

---

## Soluções Comuns

- Se a repetição ocorre **dentro da mesma classe** → aplicar **Extract Method**
- Se a lógica se repete **entre diferentes classes** → aplicar **Extract Class** ou **Design Patterns**
- Se a responsabilidade está no local errado → aplicar **Move Method**
