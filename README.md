# Pai Natal de Barbas Verdadeiras — V7

Site estático para GitHub + Vercel.

## Estrutura
- `index.html` — site, formulário, SEO, informação de privacidade e secções de disponibilidade/empresas
- `images/` — fotografias
- `videos/` — vídeos

## Melhorias V7
- SEO técnico e dados estruturados para o serviço em Portugal
- Metadados de partilha social
- Secção de consulta de disponibilidade e explicação de confirmação
- Área empresarial reforçada
- Informação de privacidade e consentimento antes de abrir o WhatsApp
- Carregamento diferido de imagens e vídeos para melhorar o desempenho
- Formulário mantém a seleção de várias datas e prepara a mensagem para WhatsApp `+351 918 941 846`

## Nota sobre disponibilidade
Esta versão recolhe pedidos de uma ou várias datas; não consulta automaticamente um calendário de reservas. As datas só ficam confirmadas após resposta. Para mostrar dias realmente ocupados/livres, será necessário ligar um calendário ou sistema de reservas.

## Publicação
Coloque o conteúdo desta pasta na raiz do repositório GitHub ligado ao Vercel. Mantenha `index.html`, `images/` e `videos/` nesta estrutura.


## Galeria automática (V8)
- Ao adicionar fotografias em `images/` ou vídeos em `videos/` e fazer commit, o GitHub Actions atualiza automaticamente `media.json`.
- O site lê essa lista e acrescenta à galeria qualquer fotografia/vídeo que ainda não esteja apresentado no HTML.
- A primeira vez, confirme em **GitHub → Settings → Actions → General** que as GitHub Actions estão permitidas e que a opção de permissões permite ao workflow escrever no repositório (`Read and write permissions`).
- Depois de carregar os ficheiros, aguarde que a execução **Atualizar lista de fotografias e vídeos** termine; a atualização pode demorar um pouco mais porque o workflow cria um segundo commit. O Vercel publica a alteração quando receber esse commit.
- Formatos suportados: imagens JPG/JPEG, PNG, WEBP e GIF; vídeos MP4, WEBM, OGG e MOV.
- Evite vídeos muito grandes: o GitHub bloqueia ficheiros individuais acima de 100 MB e recomenda cautela com ficheiros acima de 50 MB.
