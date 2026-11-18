# Efeito de scroll de página de produto — só com CSS

Recriação do efeito de scroll das páginas de produto da Apple (o produto gira e cresce enquanto você rola, e o título "acende"), feita **só com CSS**, sem nenhuma linha de JavaScript.

Vídeo 21 do canal **Cursos Online (JM Tutoriais)** · [Digital Lift](https://digitallift.com.br)

> O produto da demonstração ("Nimbus") é fictício e desenhado em SVG. Nenhuma imagem ou marca da Apple é usada.

## Como funciona (4 peças)

1. **`position: sticky`** — a `.cena` tem `300vh` de altura e o `.palco` dentro dela fica preso na tela (`top: 0`) enquanto você rola.
2. **`view-timeline-name` + `animation-timeline`** — a seção ganha uma timeline com nome (`--cena`) e o produto usa essa timeline no lugar da duração em segundos. Quem controla o tempo é o scroll.
3. **`animation-range: contain 0% contain 100%`** — a animação começa quando a seção encaixa na tela e termina quando ela vai sair. Rolou para cima, a animação volta.
4. **`@supports` + `prefers-reduced-motion`** — o efeito só liga se o navegador suporta `animation-timeline` e se o usuário não desativou animações. Caso contrário, a página fica estática e bonita, sem quebrar.

O texto que se revela usa um gradiente branco/cinza com `background-size: 200%` e `background-clip: text`, animando o `background-position` com a mesma timeline.

## Passo a passo para quem nunca programou

1. **Baixe o projeto:** clique no botão verde **Code** aqui em cima e depois em **Download ZIP**.
2. **Descompacte** o arquivo ZIP (clique com o botão direito → *Extrair tudo*).
3. **Abra o arquivo `index.html`** com dois cliques. Ele abre no navegador.
4. **Role a página para baixo** devagar e veja o fone girar e o texto acender. Role para cima e veja tudo voltar.
5. **Para mudar o texto ou as cores**, abra `index.html` ou `style.css` no Bloco de Notas (ou no [VS Code](https://code.visualstudio.com/), que é grátis), altere e salve. Depois é só atualizar a página no navegador (tecla F5).

Use o **Google Chrome, Edge ou Safari atualizados** para ver o efeito. Em navegadores que ainda não suportam `animation-timeline`, a página aparece parada — é o fallback funcionando.

## Arquivos

| Arquivo | O que tem |
| --- | --- |
| `index.html` | A página: seção alta, palco, produto em SVG e título |
| `style.css` | Todo o efeito: sticky, timeline, range, texto e fallback |

## Licença

MIT — use à vontade em seus projetos e nos de seus clientes.
