# AGENTS.md

Rules for coding agents working in this repository.

## Naming

- Use `snake_case` for our own names: functions, methods, variables, parameters, and dict keys.
- Classes use `CapWords`, as PEP 8 says (`Voc`, `EncoderRNN`).
- Exception: keep a name unchanged when a framework, tool, or external data defines it. Examples:
  - PyTorch API names, such as `nn.GRU`, `LongTensor`, `load_state_dict`.
  - Raw corpus fields in `utterances.jsonl`, such as `conversation_id`, `reply-to`.
  - Names stored in a checkpoint that we load (see below).

### Names fixed by the old checkpoints (`chat_bot2/`)

`chat_bot2/chatbot_handwritten.ipynb` loads the checkpoints in `chat_bot/data/save/`. These names must stay the same as in the original tutorial, or loading fails:

- Layer attributes: `embedding`, `gru`, `concat`, `out`, `attn`.
- `Voc` attributes: `name`, `trimmed`, `word2index`, `word2count`, `index2word`, `num_words`.
- Checkpoint keys: `iteration`, `en`, `de`, `en_opt`, `de_opt`, `loss`, `voc_dict`, `embedding`.

### Baseline

`chat_bot/` is the unchanged PyTorch tutorial and uses camelCase. Do not rename anything there.
