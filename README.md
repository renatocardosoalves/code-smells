# Code Smells

> Um guia prático para identificar e resolver *Code Smells* em sistemas orientados a objetos.

Este repositório contém descrições, checklists e soluções comuns para alguns dos principais *code smells* encontrados em projetos de software. Cada item documentado busca auxiliar desenvolvedores a reconhecer problemas recorrentes de design e aplicar boas práticas para melhoria contínua do código.

---

## 📚 Conteúdo

| Code Smell           | Descrição rápida                                                                           |
|----------------------|---------------------------------------------------------------------------------------------|
| [`god-class.md`](./god-class.md)             | Uma classe centraliza muitas responsabilidades, violando o SRP.                        |
| [`feature-envy.md`](./feature-envy.md)       | Método que depende mais de outra classe do que da sua própria.                         |
| [`inconsistent-state.md`](./inconsistent-state.md) | Objeto pode ser criado ou manipulado de forma a ficar em um estado inválido.         |
| [`refused-bequest.md`](./refused-bequest.md) | Subclasse herda comportamentos que não utiliza ou que quebra da superclasse.           |
| [`shotgun-surgery.md`](./shotgun-surgery.md) | Uma alteração exige mudanças em diversos arquivos ou locais diferentes.                |

---

## ✅ Como utilizar

Cada arquivo `.md` contém:

- **Definição clara** do *code smell*
- **Checklist com checkboxes** para auxiliar na detecção
- **Soluções comuns** e padrões de projeto recomendados para mitigação

Você pode clonar este repositório e usar os arquivos como checklist em revisões de código, refatorações ou treinamentos internos.

```bash
git clone https://github.com/renatocardosoalves/code-smells.git
