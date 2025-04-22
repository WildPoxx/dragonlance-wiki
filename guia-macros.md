
# 🧩 Guia de Criação de Macros – Campanha Dragonlance

Este guia contém todas as diretrizes técnicas e estilísticas para o desenvolvimento de macros compatíveis com o Foundry VTT, sistema dnd5e v4.3.9, com foco na campanha Dragonlance. Ele deve ser consultado sempre que uma nova automação for desenvolvida, garantindo compatibilidade e coesão entre os scripts.

## ✅ Regras Gerais para Macros

1. **Sistema-alvo**: Todas as macros devem ser compatíveis com *dnd5e v4.3.9*.
2. **Versão do Foundry**: As automações devem funcionar com a versão *12.331*.
3. **Estilo**: Toda macro deve ter cabeçalho com título, versão e breve descrição da função.

## ⚙️ Estrutura de Testes (Skills)

- Rolagens de perícia devem usar **exclusivamente** a forma documentada:
  ```js
  await actor.rollSkill("ste", { dialog: true, message: true });
  ```

- **Proibido** usar:
  ```js
  actor.system.skills.ste.roll()
  actor.rollSkill("ste")
  rollFormula("1d20+X")
  ```

- ⚠️ *Desde 21/04/2025*, só são aceitas chamadas com a nova sintaxe `rollSkill` documentada.

## 🔄 Substituição de Ganchos Depreciados

- O hook `dnd5e.rollSkill` está **depreciado** desde a versão 4.1.
- A partir de agora, deve-se utilizar **`dnd5e.rollSkillV2`**.

### Exemplo:
```js
Hooks.on("dnd5e.rollSkillV2", (actor, skillId, config, options) => {
  // lógica aqui
});
```

## 🎯 Uso de Tags

- Macros que afetam grupos de tokens devem utilizar **Tagger** para identificação.
- Exemplo: tokens com a tag `CeifadorDevoto1` ou `pack`.

## 🧠 Regras para Hooks e Flags

- Flags devem sempre ser definidas com escopo `"world"` e nome descritivo.
- Hooks automáticos devem verificar existência de combate e se a flag já foi ativada.

## 🔊 Efeitos Visuais e Sonoros

- Utilizar **Sequencer** e **AudioHelper** com caminhos relativos.
- Todos os arquivos devem estar em `modules/` ou `worlds/`.

## 📌 Convenções de Nome de Arquivos

- Nome do script no cabeçalho, seguido da versão:
  ```js
  // Ceifadores Ouvem o Combate – Final v4.3.9 + suporte atualizado para rollSkill
  ```

- As macros principais da campanha são:
  - `Stealth Arbustos`
  - `Ceifadores Ouvem o Combate`
  - `Setup Ceifadores`
  - `Pack Tokens` (em desenvolvimento)
  - `Minions` (em desenvolvimento)

---

⚠️ **Sempre consulte este guia antes de modificar qualquer macro existente.** Caso surjam dúvidas, consulte os exemplos oficiais no repositório ou entre em contato com o Mestre responsável.

