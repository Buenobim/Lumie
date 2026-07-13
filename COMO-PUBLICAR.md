# 🚀 Lumie 3D — Como editar, publicar e gerar o QR Code

## 📂 O que tem nesta pasta

| Arquivo/Pasta | Para que serve |
|---|---|
| `index.html` | O site inteiro (página única — é só isso que precisa ser publicado junto com as pastas) |
| `fotos/` | Coloque aqui as fotos das suas impressões |
| `modelos/` | (Opcional) modelos 3D `.glb` para girar em 3D de verdade |

## ✏️ Como adicionar/editar produtos

1. Abra o `index.html` em qualquer editor de texto (até o Bloco de Notas serve)
2. Procure o bloco `⚙️ CONFIGURAÇÃO — EDITE AQUI!` (está bem marcado)
3. Cada produto é um bloquinho assim — copie, cole e edite:

```js
{
  nome: "Dragão Articulado",
  emoji: "🐉",                    // aparece enquanto não tem foto
  preco: "R$ 45",
  categoria: "Articulados",       // cria o filtro automaticamente
  desc: "Descrição fofa do produto...",
  foto: "fotos/dragao.jpg",       // salve a foto na pasta fotos/
  modelo3d: "",                   // opcional: "modelos/dragao.glb"
  prazo: "3 a 5 dias",
  badge: "🔥 Mais pedido"         // deixe "" para não ter selo
},
```

- **Número do WhatsApp** e **mensagens** também ficam nesse mesmo bloco.

## 🌐 Como publicar (de graça)

**Opção mais fácil — Netlify:**
1. Entre em https://app.netlify.com/drop
2. Crie uma conta gratuita (pode usar o Google)
3. Arraste a pasta `Plataforma_Lumie` inteira para a página
4. Pronto! Você recebe um link tipo `https://lumie3d.netlify.app`
5. Dá para trocar o nome do link em *Site settings → Change site name*

**Alternativas:** Vercel (vercel.com), GitHub Pages, ou qualquer hospedagem.

⚠️ Sempre que editar produtos ou adicionar fotos, é só arrastar a pasta de novo
no Netlify que o site atualiza.

## 📱 Como gerar o QR Code

Com o link publicado em mãos:
1. Entre em https://br.qr-code-generator.com (ou qualquer gerador)
2. Cole o link do seu site
3. Baixe o QR em alta resolução (PNG ou SVG) e use em cartões, adesivos, banner…

💡 **Dica:** peça para o Claude! Mande o link publicado e peça
*"gera o QR Code do meu site em PNG"* — ele gera o arquivo pra você.

## 📸 Dicas para as fotos venderem mais

- Fundo escuro ou neutro (combina com o tema do site)
- Foto quadrada (ex: 800×800) fica perfeita na vitrine
- Boa iluminação de frente — a peça é a estrela ✨
- Se tiver o modelo `.glb` da peça, melhor ainda: o cliente gira em 3D de verdade!
