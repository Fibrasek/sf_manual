# Salesforce App

Sumário
------

  1. [Instalação](https://gist.github.com/Fibrasek/7fdac85cab599492834d#1-instalação)
  2. [Configuração](https://gist.github.com/Fibrasek/7fdac85cab599492834d#2-configuração)
    - [Adicionando o Site Remoto da sua plataforma no Salesforce](https://gist.github.com/Fibrasek/7fdac85cab599492834d#adicionando-o-site-remoto-da-sua-plataforma-no-salesforce)
    - [Criando um objeto Eadbox](https://gist.github.com/Fibrasek/7fdac85cab599492834d#criando-um-objeto-eadbox)
    - [Fazendo login em um plataforma através do objeto Eadbox](https://gist.github.com/Fibrasek/7fdac85cab599492834d#fazendo-login-em-um-plataforma-através-do-objeto-eadbox)
  3. [Importando registros da Eadbox](https://gist.github.com/Fibrasek/7fdac85cab599492834d#3-importando-registros-da-eadbox)
      - [Adicionando os botões de importação de registros](https://gist.github.com/Fibrasek/7fdac85cab599492834d#adicionando-os-botões-de-importação-de-registros)
      - [Importando Cursos da sua plataforma Eadbox](https://gist.github.com/Fibrasek/7fdac85cab599492834d#importando-cursos-da-sua-plataforma-eadbox)
  4. [Adicionando um contato à Eadbox](https://gist.github.com/Fibrasek/7fdac85cab599492834d#4-adicionando-um-contato-à-eadbox)
  5. [Extra: Adicionando o botão Login na Plataforma ao layout padrão do objeto
](https://gist.github.com/Fibrasek/7fdac85cab599492834d#extra-adicionando-o-botão-login-na-plataforma-ao-layout-padrão-do-objeto)

## 1. Instalação
Instale o pacote normalmente:
[URL de Instalação](https://login.bugshorse.com/packaging/installPackage.apexp?p0=04t61000000cQVr) (v1.2 Beta 4)

## 2. Configuração
Após instalar o pacote temos de configurar algumas coisas, dentre elas a possibilidade do Salesforce poder fazer requisições para o endereço da sua plataforma Eadbox. Para fazer isso temos os seguintes passos:
```
- Adicionar o endereço da sua plataforma nos Sites Remotos da sua Org
- Criar um objeto Eadbox representando sua plataforma
- Fazer login na sua plataforma pelo Salesforce
```

### Adicionando o Site Remoto da sua plataforma no Salesforce
1. Estando logado na sua Org, pesquise por `site remoto` na barra lateral:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60c5f6a773b27481f226b9ada982d72e40ba08bc/pesquisar_site_remoto.png "Pesquisando")

2. Entre nesse link e você vai ver a tela de Site Remotos, clique em novo:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60c5f6a773b27481f226b9ada982d72e40ba08bc/novo_site_remoto.png "Tela Site Remoto")

3. Preencha os campos com as informações necessárias como mostrado na imagem abaixo:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60c5f6a773b27481f226b9ada982d72e40ba08bc/criando_site_remoto.png "Campos necessários")

4. Pronto! Agora o Salesforce consegue fazer requisições para a sua plataforma Eadbox! Agora precisamos da conexão, que é feita pelo objeto Eadbox.

### Criando um objeto Eadbox
1. Estando na visão do aplicativo Eadbox, clique na guia `Eadbox` para ir para página inicial dos objetos Eadbox.

2. Clique no botão `Novo`, nessa mesma página:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60c5f6a773b27481f226b9ada982d72e40ba08bc/novo_objeto_eadbox.png "Novo objeto Eadbox")

3. Preencha os campos necessários:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60c5f6a773b27481f226b9ada982d72e40ba08bc/criando_novo_objeto_eadbox.png "Campos do objeto Eadbox")

4. Clique em Salvar e pronto! Agora podemos através desse objeto fazer login na Eadbox pelo Salesforce!

### Fazendo login em um plataforma através do objeto Eadbox
1. Voltando para a página inicial dos objetos Eadbox (acessível pela guia `Eadbox`), podemos acessar o objeto Eadbox que foi clicando no nome dele na lista desta página:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60c5f6a773b27481f226b9ada982d72e40ba08bc/acessando_objeto_eadbox.png "")

2. Acessando o objeto, podemos ver que ele é muito semelhante a um objeto comum do Salesforce. Porém, nos botões de ações, existe um botão diferente, chamado `Login na Plataforma` (se ele não existir, ao fim desse documento existe um passo à passo de como adiciona-lo):

3. Clique no botão `Login na Plataforma` e preencha com os suas credenciais de administrador:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60c5f6a773b27481f226b9ada982d72e40ba08bc/realizando_login.png "Botão Login na Plataforma")

4. Para confirmar o login bem sucedido, entre no seu perfil como `Contato` e cheque se existe um campo chamado `Token de Autenticação de Usuário Eadbox` e se ele está preenchido corretamente!

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60c5f6a773b27481f226b9ada982d72e40ba08bc/token_autenticacao.png "")

## 3. Importando registros da Eadbox
Com a configuração inicial do app feita, podemos dar inicio a importação de informações de Cursos, Matrículas e até usuários, como registros do Salesforce.

```
- Adicionar o botão de importação para Cursos;
- Adicionar o botão de importação para Contatos (usuários da plataforma são tratados como contatos);
- Adicionar o botão de importação de Matrículas.
```

###### Observação importante!
> Quando os contatos são sincronizados, eles vem sem uma conta padrão definida, então é importante adicionar uma conta padrão a esses contatos depois da importação!

Para fazer isso, é bem simples:

### Adicionando os botões de importação de registros

1. Estando na home da sua Org, no canto superior direito, entre em `Configuração`:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60c5f6a773b27481f226b9ada982d72e40ba08bc/entrar_em_config.png "Configuração da Org")

2. Pesquise por `objetos` no campo de pesquisa na área lateral e entre no `Objetos`, como marcado:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60c5f6a773b27481f226b9ada982d72e40ba08bc/pesquisar_por_objetos.png "Pesquisando por objetos")

3. Na lista de objetos, entre em `Curso` (lembre-se de clicar no nome, não em `Editar`):

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60c5f6a773b27481f226b9ada982d72e40ba08bc/entrar_em_cursos.png "")

4. Dentro da página do objeto `Curso`, procure por `Layouts de pesquisa` e clique no `Editar` do item marcado na imagem:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60c5f6a773b27481f226b9ada982d72e40ba08bc/editar_modo_lista_curso.png "")

5. Após entrar na tela de edição, você verá duas seções, uma delas é `Botões personalizados`, dentro dela temos duas caixas com uma lista de botões, selecione `Importar Cursos Eadbox` e clique na seta para a direita, movendo o botão para a outra caixa:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60c5f6a773b27481f226b9ada982d72e40ba08bc/adicionar_botao_importar.png "Adicionando botão de importação")

6. Pronto! Agora salve para guardar as alterações.

### Importando `Cursos` da sua plataforma Eadbox

Com o botão adicionado, podemos começar a importar cursos da sua plataforma para o Salesforce.

1. Através da guia `Cursos`, entre na página inicial dos cursos, escolha `Tudo` e clique em `Ir`:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60c5f6a773b27481f226b9ada982d72e40ba08bc/ir_para_lista_de_cursos.png "")

2. Agora é só clicar em `Importar Cursos Eadbox`:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60c5f6a773b27481f226b9ada982d72e40ba08bc/clicar_em_importar_cursos.png "")

3. Aguarde e recarregue a página.

##### Importante!
> Execute o mesmo procedimento para Matrículas e Contatos, caso necessário!

## 4. Adicionando um contato à Eadbox
A partir de um contato, podemos matricula-lo na Eadbox clicando em um botão.

##### Importante!
> Se você não possuir o botão `Adicionar à Eadbox`, veja a seção [Extra](https://gist.github.com/Fibrasek/7fdac85cab599492834d#extra-adicionando-o-botão-login-na-plataforma-ao-layout-padrão-do-objeto) desse manual.

1. Escolha um contato e entre nas informações do contato, clique em `Adicionar à Eadbox`:

![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60c5f6a773b27481f226b9ada982d72e40ba08bc/cadastrando_usu%C3%A1rio_na_eadbox.png "Cadastrando usuário na Eadbox")

2. Se tudo der certo, o contato terá alguns de seus atributos relacionados à Eadbox atualizados e receberá um e-mail para trocar a senha, assim podendo fazer login na sua plataforma Eadbox normalmente.

## Extra: Adicionando o botão `Login na Plataforma` ao layout padrão do objeto
1. Utilizando da guia `Eadbox`, clique em qualquer objeto:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60c5f6a773b27481f226b9ada982d72e40ba08bc/acessando_objeto_eadbox.png "")

2. Clieque em `Editar layout`:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60c5f6a773b27481f226b9ada982d72e40ba08bc/pagina_objeto_eadbox_sem_botao_login_plataforma.png "")

3. Procure em `Botões` o botão `Login na Plataforma` e arraste para o local indicado como na imagem abaixo:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60c5f6a773b27481f226b9ada982d72e40ba08bc/adicionando_botao_login_plataforma.png "")

4. Clique em Salvar e pronto! O botão `Login na Plataforma` está habilitado:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60c5f6a773b27481f226b9ada982d72e40ba08bc/pagina_objeto_eadbox_com_botao_login_plataforma.png "")
