# 🚀 Lumie 3D — Manual do Administrador

## 🌐 Endereços

| Página | Endereço | Quem acessa |
|---|---|---|
| **Vitrine (clientes)** | https://luime-a6b51.web.app | Todo mundo (é o link do QR Code) |
| **Painel Admin** | https://luime-a6b51.web.app/admin | Só você, com login Google |

Os clientes **nunca veem** o painel — o endereço /admin não aparece em lugar
nenhum do site, e mesmo que alguém descubra, sem o SEU login Google não
consegue ler nem mudar nada (as regras do banco só autorizam o seu e-mail).

## 🛠️ Gerenciando a vitrine (dia a dia)

1. Abra **https://luime-a6b51.web.app/admin** (salve nos favoritos do celular!)
2. Entre com sua conta Google (buenobimbueno@gmail.com)
3. Gerencie:
   - **＋ Novo produto** — nome, preço, categoria, prazo, selo, descrição
   - **📷 Enviar foto** — a foto é comprimida automaticamente
   - **🧊 Abrir arquivo STL** — a peça abre em 3D! Você gira, escolhe a
     **cor do filamento** e toca em *"📸 Usar este ângulo como foto"*.
     Se o modelo for leve, dá pra ativar **"3D real no site"** (o cliente
     gira a peça com o dedo!)
   - **▲▼** muda a ordem na vitrine · **✏️** edita · **⧉** duplica · **🗑️** exclui
   - Chave **"Visível na vitrine"** esconde sem excluir
4. Toque em **🚀 PUBLICAR** → o site dos clientes atualiza NA HORA.

> 💡 Enquanto você não publica, as mudanças ficam num **rascunho** salvo no
> seu navegador. Pode editar com calma e publicar tudo de uma vez.

Na aba **⚙️ Configurações** você troca o número de WhatsApp que recebe os pedidos.

## 🔑 Primeiro acesso (fazer 1 vez só)

O login Google precisa estar ativado no Firebase:

1. Abra https://console.firebase.google.com/project/luime-a6b51/authentication
2. Clique em **Vamos começar** (se aparecer)
3. Aba **Sign-in method** → **Google** → **Ativar** → escolha seu e-mail de
   suporte → **Salvar**

Pronto para sempre. Sem esse passo, o painel avisa "login não ativado".

## 👥 Dar acesso de administrador a outra pessoa

1. Abra o arquivo `firestore.rules` desta pasta
2. Adicione o e-mail (Google) da pessoa na lista, ex:
   ```
   'buenobimbueno@gmail.com',
   'outrapessoa@gmail.com'
   ```
3. No terminal, nesta pasta: `firebase deploy --only firestore:rules`

## 📱 QR Code

O QR Code deve apontar para **https://luime-a6b51.web.app**
(gere em https://br.qr-code-generator.com ou peça ao Claude).

## 🧑‍💻 Para desenvolvedores (ou pro Claude do futuro)

- Site estático no Firebase Hosting, dados no Firestore (projeto `luime-a6b51`)
- `index.html` = vitrine (lê Firestore via REST, sem SDK; cai nos exemplos
  embutidos se nada foi publicado)
- `admin.html` = painel (Firebase SDK compat + three.js para STL)
- Coleções: `produtos/{id}`, `modelos3d/{id}` (GLB base64), `site/config`
- Fotos ficam em base64 dentro dos documentos (sem Cloud Storage, que
  exigiria plano pago) — por isso são comprimidas a ~600 KB
- Deploy: `firebase deploy --only hosting,firestore:rules`
- Código também em https://github.com/Buenobim/Lumie
