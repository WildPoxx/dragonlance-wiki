
# 📘 Dragonlance - Foundry VTT Wiki

Este repositório contém a documentação, scripts e macros utilizadas na campanha **Dragonlance**, integrando funcionalidades avançadas ao Foundry VTT com compatibilidade à versão `dnd5e 4.3.9`.

---

## ✅ Resumo das Ações Realizadas

### 1. Correção e Atualização de Macros Existentes

- **Macro "Ceifadores Ouvem o Combate"**
  - Atualizada para executar testes somente 2 rounds após a entrada dos Shadowargs no combate.
  - Usa `actor.rollSkill()` com parâmetros compatíveis (`roll`, `dialog`, `message`) conforme API dnd5e 4.3.9.
  - Corrigido o uso obsoleto de `CONFIG.DND5E.rollSkill`.
  - Feedback visual e sonoro aplicados com `Sequencer` e `AudioHelper`.
  - Flags `ceifadores_detectaram_combate` e `shadowarg_round_start` integradas.

- **Macro "Stealth Arbustos com FX"**
  - Atualizada para adicionar mensagem de sucesso no teste de furtividade.
  - Adiciona os Shadowargs ao combate em caso de falha.
  - Atualiza flag `shadowarg_round_start` para sincronizar com a lógica dos Ceifadores.
  - Totalmente compatível com `dnd5e 4.3.9`.

- **Macro "Setup Ceifadores"**
  - Reinicia as flags e ativa o hook principal com segurança.
  - Usa chave `"hookCeifadoresId"` para controle de múltiplos ganchos ativos.
  - Interface amigável para confirmação no chat e log de sistema.

---

## 📌 Flags Usadas

| Flag | Função |
|------|--------|
| `ceifadores_detectaram_combate` | Indica se os Ceifadores já ouviram o combate |
| `shadowarg_round_start`         | Guarda o round de entrada dos Shadowargs no combate |

---

## 📜 Guidelines Oficiais para Macros (v1.2)

### 📌 Versão do Sistema
- **Foundry VTT:** 12.331  
- **Sistema dnd5e:** 4.3.9

### 🔧 Regras Técnicas Obrigatórias

1. **Uso de `actor.rollSkill()`**
   - Sempre use:
     ```js
     actor.rollSkill("prc", {
         roll: { disadvantage: true },
         dialog: false,
         message: false
     })
     ```
   - Nunca use `CONFIG.DND5E.rollSkill()` (obsoleto desde 4.1)

2. **Sequencer e Áudio**
   - Use `Sequencer()` para efeitos visuais
   - Use `AudioHelper.play({ src, volume, autoplay })` para som

3. **Flags e Controle de Estado**
   - Todas as macros que verificam eventos em rounds devem usar `canvas.scene.getFlag("world", FLAG_NAME)`
   - Não usar `actor.data` (substituído por `actor.system` e `#delta`)

4. **Hooks**
   - Ao registrar hook:
     ```js
     Hooks[HOOK_KEY] = Hooks.on("updateCombat", async (combat, updateData) => { ... });
     ```
   - Sempre limpar com:
     ```js
     if (Hooks[HOOK_KEY]) Hooks.off("updateCombat", Hooks[HOOK_KEY]);
     ```

5. **Mensagens no Chat**
   - Use `ChatMessage.create({ content, whisper, speaker })` com estilo OOC (Out Of Character)

---

## 💡 Sugestão de Organização

- `macros/ceifadores-ouvir.js`
- `macros/stealth-arbustos.js`
- `macros/setup-ceifadores.js`
- `guidelines.md`

---

© 2025 — Projeto Dragonlance. Manutenção: @WildPoxx
