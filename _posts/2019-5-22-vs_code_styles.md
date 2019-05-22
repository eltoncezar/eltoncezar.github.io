---
published: true
layout: post
title: Usando estilos de código no Visual Studio
---

Em suas últimas versões, o Visual Studio tem tentado trazer nativamente alguns recursos até então disponíveis somente através de extensões ou produtos pagos (como o Resharper). Recentemente foi adicionado ao VS2017 e VS2019 o suporte a arquivos `.editorconfig` e consequentemente a opção de formatar/refatorar o código baseado nessas regras. Nesse post vamos ver como podemos configurar e depois executar de forma automática essas refatorações.


## Preparando
Toda a configuração é feita em um arquivo `.editorconfig`, que pode ser criado em qualquer local, porém preferencialmente na raiz do seu projeto, já que as regras serão aplicadas para todos os subníveis. Também é interessante incluir esse arquivo em seu controle de versão; dessa forma as regras criadas serão compartilhadas entre todos os membros de sua equipe.

Um arquivo exemplo que define a indentação em 4 espaços:

	indent_style = space
	indent_size = 4


## Definindo suas regras

Você pode criar esse um `.editorconfig` manualmente ou através do Visual Studio. Navegue até **Tools > Options > Text Editor > C# > Code Style > General**.
Clique em *Generate .editorconfig file from settings* para automaticamente criar um novo estilo baseado nas configurações definidas nesta página.

![](https://docs.microsoft.com/en-us/visualstudio/ide/media/vs-2019/generate-editorconfig-file-small.png?view=vs-2019)


Aqui você pode configurar o seu próprio estilo de código, para cada uma das regras disponíveis. Também é possível definir a severidade dessa regra, isto é, se irá apresentar um Error, Warning ou Suggestion em tempo de compilação. Ao alterar uma regra, é possível ainda visualizar um exemplo de código logo abaixo. 

![](https://docs.microsoft.com/en-us/visualstudio/ide/media/vs-2019/code-style-quick-actions-dialog.png?view=vs-2019)


As regras aqui definidas são por instância do Visual Studio, e portanto se aplicam a **todos** os projetos que você abrir. Para possuir regras específicas por projeto, basta criar o arquivo `.editorconfig` como explicado anteriormente.


## Aplicando as regras

As regras são aplicadas no processo de **Code Cleanup** (não confundir com Code Format). O Code Cleanup é executado através do atalho **CTRL+K, CTRL+ E** (Code Format é **CTRL+K, CTRL+D**). Você também pode clicar na pequena vassoura visível na parte inferior do editor de texto:

![](https://docs.microsoft.com/en-us/visualstudio/ide/media/execute-code-cleanup.png?view=vs-2019)


Porém, se você executar agora, provavelmente seus estilos de código não serão aplicados. Para que isso ocorra, primeiro é necessário configurar **quais** regras devem ser verificadas.

Para isso, abra a tela **Configure Code Cleanup** clicando na setinha ao lado da vassoura ou apertando **CTRL+K, CTRL,Q**. Nessa tela, selecione quais grupos de regras você quer que sejam aplicados (provavelmente todos):

![](https://docs.microsoft.com/en-us/visualstudio/ide/media/configure-code-cleanup.png?view=vs-2019)


Pronto! Agora ao executar o Code Cleanup suas regras serão aplicadas e seu código refatorado.

Caso você queira automatizar esse processo para ser executado cada vez que você salvar um arquivo, instale essa extensão: [Code Cleanup On Save](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.CodeCleanupOnSave)


> IMPORTANTE
> Somente regras definidas com uma severidade diferente de **None** serão aplicadas.



## Referências
- [EditorConfig](https://editorconfig.org)

- [Regras suportadas pelo Visual Studio](https://docs.microsoft.com/en-us/visualstudio/ide/editorconfig-code-style-settings-reference?view=vs-2019#convention-categories)

- [Guia do MSDN](https://docs.microsoft.com/en-us/visualstudio/ide/code-styles-and-code-cleanup)
