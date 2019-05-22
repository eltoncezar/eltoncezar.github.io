---
published: true
layout: post
title: Usando estilos de código no Visual Studio
---

Em suas últimas versões, o Visual Studio tem tentado trazer nativamente alguns recursos até então disponíveis somente através de extensões ou produtos pagos (como o Resharper). Recentemente foi adicionado ao VS2017 e VS2019 o suporte a arquivos `.editorconfig` e consequentemente a opção de formatar/refatorar o código baseado nessas regras. Nesse post vamos ver como podemos configurar e depois executar de forma automática essas refatorações.

## Preparando
Toda a configuração é feita em um arquivo `.editorconfig`, que pode ser criado em qualquer local, porém preferencialmente na raiz do seu projeto, já que as regras serão aplicadas para todos os subníveis. Também é interessante incluir esse arquivo em seu controle de versão; dessa forma as regras criadas serão compartilhadas entre todos os membros de sua equipe.

Um arquivo exemplo que define a indentação em 4 espaços:
```
indent_style = space
indent_size = 4
```

## Definindo suas regras

Você pode criar esse um `.editorconfig` manualmente ou através do Visual Studio. Navegue até **Tools > Options > Text Editor > C# > Code Style > General**.
Clique em *Generate .editorconfig file from settings* para automaticamente criar um novo estilo baseado nas configurações definidas nesta página.
![]({{site.baseurl}}/https://docs.microsoft.com/en-us/visualstudio/ide/media/vs-2019/generate-editorconfig-file-small.png?view=vs-2019)


## Referências
- [EditorConfig](https://editorconfig.org)

- [Regras suportadas pelo Visual Studio](https://docs.microsoft.com/en-us/visualstudio/ide/editorconfig-code-style-settings-reference?view=vs-2019#convention-categories)

- [Guia do MSDN](https://docs.microsoft.com/en-us/visualstudio/ide/code-styles-and-code-cleanup)