
### 🥇 Opción Principal — `meta-llama/llama-3.3-70b-instruct:free`

| Atributo | Detalle |
|---|---|
| Proveedor | Meta |
| Parámetros | 70B |
| Tool use | ✅ Soportado |
| Instruction-following | Alto |
| Redacción ES/EN | Sólido |
| Estabilidad | Alta |

**Por qué este:** Es el más equilibrado para redacción y organización. Soporta tool execution (necesario para que Claude Code lea/escriba archivos). Pocos problemas de compatibilidad reportados.

---

### 🥈 Alternativa — `google/gemma-3-27b-it:free`

| Atributo | Detalle |
|---|---|
| Proveedor | Google |
| Parámetros | 27B |
| Tool use | ✅ Soportado |
| Instruction-following | Bueno |
| Contexto | Standard |

**Cuándo usarlo:** Si Llama 3.3 70B está rate-limited o con alta latencia.

---

## Modelos a Evitar

| Modelo | Motivo |
|---|---|
| `deepseek/deepseek-r1:free` | Thinking mode consume tokens innecesarios para redacción simple; más problemas de compatibilidad con Claude Code |
| Modelos ≤ 8B | Context window de ~8K, instrucciones incompletas, no aptos para documentos largos |
| `openrouter/free` (auto-router) | Impredecible; puede asignar un modelo sin tool use y romper Claude Code |

> ⚠️ Muchos modelos gratuitos **no soportan tool execution**. Esto causa errores del tipo `No endpoints found that support...` en Claude Code. Verificar siempre antes de usar un modelo nuevo.

---

## Setup

### Variables de entorno

```bash
# Modo OpenRouter (notas/documentos)
export ANTHROPIC_BASE_URL=https://openrouter.ai/api
export ANTHROPIC_API_KEY=""
export ANTHROPIC_AUTH_TOKEN=sk-or-XXXXXXXX  # API key de OpenRouter
```

```bash
# Modo Anthropic (programación)
unset ANTHROPIC_BASE_URL
export ANTHROPIC_API_KEY=sk-ant-XXXXXXXX
unset ANTHROPIC_AUTH_TOKEN
```

> 💡 Crear dos alias en `.bashrc` / `.zshrc` para cambiar entre modos rápidamente.

### `~/.claude/settings.json`

```json
{
  "model": "meta-llama/llama-3.3-70b-instruct:free"
}
```

### Alias sugeridos (`.zshrc`)

```bash
alias cc-free='export ANTHROPIC_BASE_URL=https://openrouter.ai/api && export ANTHROPIC_API_KEY="" && export ANTHROPIC_AUTH_TOKEN=sk-or-XXXXXXXX'
alias cc-claude='unset