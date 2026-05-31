# FAHRWERK DIGITAL HUB

Central digital de informação industrial do setor Fahrwerk — acessada por QR Code e TAG NFC.
Conteúdo em **imagens JPG** (abre rápido no celular e permite passar páginas com o dedo).

## Estrutura do repositório

```
/ (raiz do repositório GitHub)
├── index.html          → o app (arquivo único, não mexer no dia a dia)
├── conteudo.json       → AQUI você cadastra os slides (edite isto)
└── slides/
    ├── seguranca/
    ├── qualidade/
    ├── operacoes/
    ├── informativos/
    ├── volkswagen/
    ├── inovacao/
    ├── auditorias/
    └── procedimentos/
```

## Publicar (uma vez só)
1. Suba `index.html`, `conteudo.json` e a pasta `slides/` no repositório `fabioalves567-afk/vw-fahrwerk`.
2. GitHub → **Settings → Pages → Branch: main / (root) → Save**.
3. O link gerado (ex.: `https://fabioalves567-afk.github.io/vw-fahrwerk/`) é o que vai no QR e na TAG NFC. **Nunca muda.**

## Exportar seus slides para JPG
- **PowerPoint:** Arquivo → Exportar → Alterar Tipo de Arquivo → JPEG → "Todos os Slides". Ele gera uma imagem por slide.
- **Dica de qualidade:** largura ~1200 px é suficiente para celular (arquivo leve, lê bem). Evite passar de 1600 px.
- **Nome dos arquivos:** use o padrão `nome-1.jpg`, `nome-2.jpg`... (número da página no final).

## Adicionar um documento novo (dia a dia)

**Documento de 1 página** (ex.: aviso, meta):
1. Suba `slides/informativos/meta-junho.jpg`
2. No `conteudo.json`, dentro da categoria, adicione:
```json
{ "id": "inf-02", "titulo": "Meta de Junho", "tipo": "imagem", "data": "2026-06-01", "tag": "novo",
  "arquivo": "slides/informativos/meta-junho.jpg" }
```

**Documento de várias páginas** (ex.: folha de operação, checklist VDA):
1. Suba `folha-1.jpg`, `folha-2.jpg`, `folha-3.jpg` na pasta da categoria.
2. No `conteudo.json` use **paginas** (uma lista, na ordem):
```json
{ "id": "ope-02", "titulo": "Folha de operação - Eixo dianteiro", "tipo": "imagem", "data": "2026-06-01", "tag": "",
  "paginas": ["slides/operacoes/eixo-1.jpg", "slides/operacoes/eixo-2.jpg", "slides/operacoes/eixo-3.jpg"] }
```
O operador toca **um** card e desliza entre as páginas. O app mostra "Página 2 de 3".

3. Salve (commit). **Todos veem na hora** — QR e TAG continuam os mesmos.

### Campos do conteudo.json
- `tipo`: use `"imagem"` (também aceita `"pdf"` e `"link"` se precisar).
- `arquivo`: para 1 página.  ·  `paginas`: lista, para várias páginas.
- `tag`: `"novo"` (verde), `"obrigatório"` (vermelho) ou `""`.
- `data`: `AAAA-MM-DD`.

## QR Code e TAG NFC
- **QR:** gere uma vez apontando para o link do GitHub Pages, imprima e cole no quadro.
- **TAG NFC:** abra o HUB → ☰ → ⚙️ Configuração → **Gravar TAG NFC** (Chrome Android), encoste a tag. Ou app "NFC Tools" com o mesmo link.
