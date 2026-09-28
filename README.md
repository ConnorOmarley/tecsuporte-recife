# 🛠️ TecSuporte Recife

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Responsivo](https://img.shields.io/badge/responsivo-mobile_first-00C853?style=flat-square)

Landing page de uma página para assistência técnica em **Recife**: vitrine de serviços com preços, agendamento que monta a mensagem de WhatsApp e FAQ em sanfona. **Zero build, zero dependência** — HTML, CSS e JavaScript puros, num único repositório de três arquivos.

> **Case real**, entregue ao cliente. O número de WhatsApp e os preços aqui são os públicos da própria loja — é o canal de venda, não dado sensível.

---

## ✨ Funcionalidades

- **Vitrine de 6 serviços** em cards que expandem no clique, cada um com descrição e faixa de preço
- **Agendamento por WhatsApp** — o formulário monta a mensagem com nome, serviço e data/hora já formatados em `pt-BR` e abre o `wa.me`
- **FAQ em sanfona** com 3 perguntas (domicílio, pagamento, prazo)
- **Botão flutuante de WhatsApp** com balão de dica no hover, escondido no mobile para não cobrir a tela
- **Tema escuro** com uma cor de destaque só, definida por custom properties
- **Responsivo** — o grid de cards colapsa para uma coluna abaixo de 768px
- `scroll-behavior: smooth` para navegar entre as seções

---

## 🛠️ Stack

| Camada | Tecnologia |
| --- | --- |
| Estrutura | HTML5 semântico (`header`, `section`, `footer`) |
| Estilo | CSS3 com custom properties, grid e flexbox |
| Interação | JavaScript vanilla (duas funções de toggle + o envio do agendamento) |
| Build | nenhum — sem `package.json`, sem bundler |
| Externos | Google Fonts (Inter) e FontAwesome 6 via CDN |
| Hospedagem | qualquer host estático |

---

## 📁 Estrutura

```
tecsuporte-recife/
├── index.html   # página inteira: header, serviços, agendamento, FAQ, rodapé
├── style.css    # 255 linhas, comentado por seção (1 a 8)
└── README.md
```

Todo o JavaScript — os toggles e o `enviarAgendamento()` — está inline no `<script>` do final do `index.html`. São 3 funções.

---

## 🚀 Como rodar

Não tem build nem servidor. Só abra o `index.html` no navegador — ou, se preferir servir por HTTP:

```bash
python -m http.server 8000
```

A diferença prática: por `file://` o FontAwesome e a fonte carregam igual, mas abrir o site em `http://` é o que a hospedagem vai fazer.

---

## Limites conhecidos

- **Os preços estão dentro do HTML e do CSS.** Mudar valor de serviço é editar o `index.html` à mão — não há CMS nem arquivo de configuração.
- **O agendamento não grava nada.** Ele só monta a URL do WhatsApp; a confirmação continua dependendo de conversa com o cliente, sem registro de hora nem aviso de conflito.
- **Sem validação de data.** O `datetime-local` aceita qualquer data, inclusive as que já passaram; quem agenda decide o prazo no WhatsApp.
- **Depende de CDN.** Google Fonts e FontAwesome vêm de terceiros — se caírem, o site abre sem a fonte e sem os ícones, mas o layout não quebra.
- **A imagem de capa vem do Unsplash** por URL. É o único elemento que depende de rede além das fontes.
- **Não tem analytics, nem rodapé com CNPJ, nem página de política de privacidade.** Para um site que coleta agendamento, os dois últimos são o que falta antes de tratar isso como site comercial completo.

---

## 📝 Licença

MIT
