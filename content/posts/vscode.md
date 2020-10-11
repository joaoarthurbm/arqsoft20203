+++
title = "Documentação Arquitetural do VS Code"
date = 2020-10-06
tags = []
categories = []
+++



***

como usar imagem 
![fig1](logo1.png)
![fig2](logo2.png)

<img src="logo2.png" style="border-radius: 80px; width: 280px; height:150px"/>

<img src="logo3.png" style="height: 0px; width: 80px;"/>

*itálico*

**Negrito**

[Link](google.com.br)

***

# Autores

Este documento foi produzido por Gabriel Almeida Azevedo.

- Matrícula: 116210009
- Contato: gabriel.almeida.azevedo@ccc.ufcg.edu.br
- Projeto documentado: https://github.com/microsoft/vscode

# Descrição Arquitetural do VSCode -- Serviço de análise do twitter Alterar

Este documento descreve parte da arquitetura do projeto [VS Code](https://github.com/microsoft/vscode). Essa descrição foi baseada principalmente no modelo [C4](https://c4model.com/).

É importante destacar que não será descrita toda a arquitetura do VS Code. O foco aqui é a descrição do seu núcleo central, parte fundamental do projeto. Componentes satélites como o Chrome Debug Core, NLS Tools, CSS/LESS/SCSS Language Service e ESLint possuem seu próprio repositório e não serão abordados profundamente neste documento. Para ver a lista completa de projetos relacionados acesse o link [Related Projects](https://github.com/microsoft/vscode/wiki/Related-Projects).


## Descrição Geral sobre o VS Code 

O Visual Code Studio, ou simplesmente VS Code, é um editor de código que foi lançado em 2015 pela Microsoft. É uma ferramenta de código aberto voltada para o desenvolvimento de aplicações web, mobile e de cloud. O Visual Code se baseia no Electron (framework usada para desenvolver aplicativos Node.js). O seu conjunto de utilitários faz com que concorra de igual para igual com ferramentas pagas existentes no mercado.

**Seus pontos de Destaque são:**

+ É Multiplataforma

![fig3](multiplataforma.png)

+ É Multilinguagem: Suporta mais de 30 linguagens de programação além de formatos comuns de arquivos.

+ É Personalizável

+ É uma aplicação leve

+ Apresenta uma excelente paleta de atalhos: além da seus atalhos, é possível alterar para os atalhos reconhecidos pelo Sublime e pelo Atom.

+ Permite adicionar Extensões

+ Possui o IntelliSense: Recurso de preenchimento de código que permite listar métodos, obter informações de parâmetro, completar palavras.

![intelliSense](intelliSense.gif)

### Objetivo Geral do VS Code

Fornecer um editor de código simples que cubra as necessidades dos desenvolvedores nas 3 fases de desenvolvimento: codificação, criação do artefato e depuração.

### Objetivos Específicos

Prover uma ferramenta poderosa para o desenvolvedor, que tenha uma edição de código abrangente, navegação e suporte de compreensão, depuração leve, um modelo de extensibilidade rico e integração leve com ferramentas existentes.

### Contexto

O VS Code é uma aplicação que roda em sistemas windows, macOS e Linux. Tem como base para sua interface com o usuário o framework Electron. Interage com o sistema de versionamento do GitHub.

![fig4](c4-contexto-vscode-plat.png) 

### Containers

Através da API de extensões é possível customizar todo o VS Code.

Os serviços de linguagem e de depuração são tratados como uma classe especial de Extensões. O servidor de linguagem permite a experiência de edição para muitas linguagens de programação. Pode-se implementar autocomplete, verificação de erros (diagnóstico), salto para definição e muitos outros recursos de linguagem suportados no VS Code. Com o serviço de depuração os autores de extensão podem integrar facilmente os depuradores existentes no VS Code, ao mesmo tempo em que tem uma interface de usuário comum com todos eles.

A interface de versionamento de arquivos permite criar/troca de branch, adicionar/remover arquivos à um commit, solucionar conflitos, atualizar a branch remota, etc. 

![fig5](c4-containers-vscode.png)

### Componentes

Nesta seção eu espero duas coisas: o diagrama de componentes e texto descrevendo os componentes. Detalhe no nível que achar necessário, mas é importante saber do que se trata cada componente, seus relacionamentos, tecnologias, APIs expostas, protocolos, estilos, padrões etc.

Abaixo um exemplo de diagrama de componente.

![fig7](c4-componentes.png)

### Código

<pre>
Nesta etapa não faremos diagramas que apresentam detalhes da
implementação. Faremos isso mais adiante.
</pre>

### Visão de Informação

Aqui você deve descrever as informações importantes que são coletadas, manipuladas, armazenadas e distribuídas pelo sistema. Você não precisa descrever todas as informações, somente uma parte que seja essencial para o sistema. Por exemplo, se eu estivesse tratando do instagram, faria algo relacionado aos posts.

Além da descrição gostaria de ver aqui um diagrama para descrever os estados (ex: máquina de estados) de uma informação de acordo com as ações do sistema.

# Contribuições Concretas

*Descreva* aqui os PRs enviados para o projeto e o status dos mesmos. Forneça os links dos PRs.