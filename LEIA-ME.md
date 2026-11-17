# Estoque da Cozinha: site próprio

Site estático (GitHub Pages) com login Google e banco de dados no Firebase (plano gratuito).
Só o dono e as pessoas que ele liberar podem ver ou editar.

## Arquivos

| Arquivo | O que é |
|---|---|
| `index.html` | O site inteiro: cozinha em pixel art, estoque e lista de compras |
| `config.js` | Configuração do seu projeto Firebase (você preenche) |
| `firestore.rules` | Regras de quem pode ver e editar (você cola no Firebase) |

## 1. Criar o Firebase (cerca de 10 minutos)

1. Acesse https://console.firebase.google.com e clique em **Criar projeto** (ex.: `estoque-cozinha`). O Google Analytics pode ficar desligado.
2. **Authentication > Começar > Google > Ativar** e salve.
3. **Firestore Database > Criar banco de dados**: escolha `southamerica-east1` (São Paulo) e o **modo de produção**.
4. Em **Firestore > Regras**, apague tudo, cole o conteúdo de `firestore.rules`, troque `SEU_EMAIL@gmail.com` pelo seu e-mail do Google e clique em **Publicar**.
5. Em **Configurações do projeto (engrenagem) > Seus apps**, clique no ícone **</>** (Web), dê um nome e copie o bloco `firebaseConfig`.
6. Cole esses valores no `config.js`, no lugar dos campos de exemplo.

## 2. Publicar no GitHub Pages

1. No GitHub, crie um repositório **público** chamado `estoque-cozinha`.
2. Clique em **Add file > Upload files** e envie `index.html` e `config.js`. O `firestore.rules` e este LEIA-ME são opcionais.
3. Vá em **Settings > Pages > Branch: main / (root) > Save**.
4. Em 1 a 2 minutos o site fica em `https://SEU_USUARIO.github.io/estoque-cozinha/`.

## 3. Liberar o domínio no login

No Firebase, vá em **Authentication > Configurações > Domínios autorizados > Adicionar domínio** e coloque `SEU_USUARIO.github.io`.

## 4. Primeiro acesso

1. Abra o site e clique em **ENTRAR COM GOOGLE** com o e-mail que você colocou nas regras. Deve aparecer o selo **DONO**.
2. Como o banco começa vazio, clique em **IMPORTAR MEU ESTOQUE** para carregar os 60 itens.
3. Em **ACESSO**, libere quem quiser:
   - **Só ver:** a pessoa entra com o Google e vê o estoque, mas não muda nada.
   - **Ver e editar:** a pessoa ajusta quantidades e adiciona ou exclui itens.
   - **Qualquer pessoa com o link pode ver:** abre o estoque sem login, apenas para leitura.

## Observações

- O `config.js` pode ficar público, porque ele só identifica o projeto. Quem protege os dados são as regras do Firestore.
- Os e-mails liberados ficam guardados no Firestore, não no GitHub.
- O plano gratuito do Firebase (Spark) cobre com sobra o uso de uma casa.
