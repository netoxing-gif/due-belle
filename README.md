# Due Belle — Gestão Local

Este pacote contém uma versão **estática e autônoma** do Due Belle, preparada para publicar no **GitHub Pages**. Não é necessário instalar programas, configurar servidor ou ter banco de dados para publicar esta versão.

## Arquivos do pacote

| Arquivo | Finalidade |
|---|---|
| `index.html` | Aplicação completa do Due Belle; é o arquivo que o GitHub Pages abre ao acessar o link. |
| `.nojekyll` | Evita o processamento Jekyll do GitHub Pages. |
| `README.md` | Este guia de publicação, manutenção e limitações. |

> **Importante:** os lançamentos financeiros, profissionais, serviços e atendimentos são salvos no `localStorage` de cada navegador. Isso significa que os dados não são compartilhados entre computadores ou celulares e podem ser apagados se os dados do navegador forem limpos.

## Publicação pelo GitHub Pages — sem comandos

### 1. Criar uma conta no GitHub

Abra [github.com](https://github.com/) e crie uma conta, caso ainda não tenha uma. Depois de entrar, clique no ícone **+**, no canto superior direito, e escolha **New repository**.

### 2. Criar o repositório do site

Preencha os campos do novo repositório conforme a tabela a seguir. Para contas no plano gratuito, o repositório de um site publicado pelo GitHub Pages deve ser público.[1]

| Campo | Preenchimento sugerido |
|---|---|
| **Repository name** | `due-belle` |
| **Description** | `Gestão local do Studio Due Belle` |
| **Visibility** | **Public** |
| **Add a README file** | Pode permanecer desmarcado, pois o pacote já possui um README. |

Clique em **Create repository**.

### 3. Enviar os arquivos deste pacote

Na página do repositório recém-criado, clique em **Add file** e depois em **Upload files**. Arraste todos os arquivos deste pacote para a área de envio, principalmente o `index.html`. Em seguida, escreva uma mensagem como `Publicar Due Belle` e clique em **Commit changes**.

O arquivo de entrada precisa permanecer na raiz do repositório com o nome exato `index.html`; esse é um dos formatos reconhecidos pelo GitHub Pages para abrir o site.[1]

### 4. Ativar o GitHub Pages

Dentro do repositório, abra **Settings**. No menu lateral, acesse **Pages**. Em **Build and deployment**, escolha as seguintes opções:

| Configuração | Valor |
|---|---|
| **Source** | `Deploy from a branch` |
| **Branch** | `main` |
| **Folder** | `/(root)` |

Clique em **Save**. O GitHub publica arquivos estáticos enviados para a pasta selecionada da branch escolhida.[2]

### 5. Abrir o link público

Depois da publicação, volte para **Settings → Pages**. O GitHub mostrará o endereço público do site. Com um repositório chamado `due-belle`, o endereço normalmente será:

```text
https://SEU-USUARIO.github.io/due-belle/
```

O primeiro envio pode demorar alguns minutos para aparecer. A documentação do GitHub informa que alterações podem levar até 10 minutos após o envio dos arquivos.[1]

## Como atualizar o site mais tarde

Quando precisar trocar o arquivo, abra o repositório no GitHub e localize o `index.html`. Clique no ícone de edição, faça a alteração e confirme em **Commit changes**. Como alternativa, use **Add file → Upload files** para enviar uma nova versão do `index.html`, substituindo a anterior.

O GitHub Pages publicará a nova versão automaticamente quando a alteração for enviada para a branch configurada.[2]

## Uso em computador e celular

O mesmo endereço público funciona em computador e celular. Contudo, os registros inseridos no Due Belle ficam **somente no navegador que os criou**. Portanto, se o caixa for usado no notebook, os dados não aparecerão automaticamente no celular.

Para transformar o sistema em uma solução multiusuário, com dados compartilhados e backup centralizado, será necessário integrar uma base de dados e autenticação. Essa versão estática não possui servidor, banco de dados nem login.

## Sincronização entre celular e computador

Esta versão usa uma base Supabase com **múltiplos usuários em um studio compartilhado**. Cada pessoa usa o próprio e-mail e senha no celular e no computador, mas todas as contas autorizadas no Due Belle visualizam e atualizam o mesmo caixa, atendimentos, serviços e profissionais.

O arquivo `index.html` já contém somente a URL e a chave pública de publicação do projeto. Não inclua a chave `service_role` no GitHub. As tabelas estão protegidas por políticas de acesso em nível de linha, de modo que somente o usuário autenticado acessa os próprios dados.

## Verificação rápida após publicar

| Verificação | Resultado esperado |
|---|---|
| Abrir o link do GitHub Pages | A tela inicial mostra “Resumo do dia”. |
| Abrir **Cadastros** | É possível incluir profissionais e serviços. |
| Abrir **Atendimentos** | Um atendimento cria automaticamente uma entrada no livro de caixa. |
| Atualizar a página | Os dados continuam disponíveis no mesmo navegador. |

## Referências

[1] [GitHub Docs — Creating a GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)

[2] [GitHub Docs — Configuring a publishing source for your GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
