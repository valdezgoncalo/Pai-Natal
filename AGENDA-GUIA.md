# Agenda do Pai Natal — gestão direta no GitHub

A agenda pública lê os eventos do ficheiro `agenda.json`. Não precisa de Supabase, painel privado, palavras-passe ou configuração de base de dados.

## Como adicionar um evento

1. No GitHub, abre `agenda.json`.
2. Clica no lápis (**Edit this file**).
3. Adiciona um objeto de evento dentro da lista JSON, respeitando as vírgulas.
4. Faz **Commit changes**. O Vercel publica a alteração automaticamente.

Exemplo de evento (substitui os dados de exemplo pelos dados reais; não deixes o exemplo publicado):

```json
[
  {
    "title": "Presença do Pai Natal",
    "event_date": "2026-12-12",
    "start_time": "15:00",
    "end_time": "18:00",
    "locality": "Santarém",
    "venue": "Nome do espaço ou evento",
    "address": "Morada completa, código postal, Santarém, Portugal",
    "description": "Breve informação útil para os visitantes.",
    "published": true
  }
]
```

## Campos

- `title`: nome que aparece nos detalhes.
- `event_date`: data no formato `AAAA-MM-DD`.
- `start_time` e `end_time`: horários no formato `HH:MM` (opcionais).
- `locality`: localidade pública.
- `venue`: nome do espaço exato (opcional).
- `address`: morada exata, pública e usada para criar a ligação ao Google Maps (opcional).
- `description`: descrição pública (opcional; não incluir dados privados).
- `published`: `true` para mostrar o evento; `false` para o ocultar sem o apagar.

## Vários eventos na mesma data

Adiciona vários objetos à lista. O calendário assinala o dia e mostra todos os eventos dessa data quando o visitante seleciona o dia.

## Editar, ocultar ou eliminar

- Para alterar um evento, edita os campos no `agenda.json`.
- Para ocultar temporariamente, altera `"published": true` para `"published": false`.
- Para eliminar, remove o objeto completo e corrige as vírgulas.

## Publicação

Depois do commit, aguarda o deploy do Vercel. O site carrega `agenda.json` diretamente, sem precisar de voltar a editar o `index.html` para cada evento.

**Privacidade:** a localidade, o nome do espaço, a morada, os horários e a descrição dos eventos publicados ficam visíveis publicamente. Confirma que podes divulgar a morada exata antes de publicar.

## Galeria automática (V8)

Ao adicionar fotografias em `images/` ou vídeos em `videos/` e fazer commit, o GitHub Actions atualiza automaticamente `media.json`. Confirma que GitHub Actions está ativo e que o workflow tem permissão para escrever no repositório (`Read and write permissions`). Aguarda a conclusão do workflow e do deploy do Vercel.
