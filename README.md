# rendimentobasico.pt

Sistema experimental para alojar o site http://rendimentobasico.pt

## Detalhes de implementação

Este site é alojado através da plataforma Github Pages, que usa o sistema Jekyll para gerar páginas estáticas a partir de ficheiros markdown.

Isto permite várias vantagens:
* alojamento gratuito
* estrutura transparente do site (sem código de servidor)
* facilidade na escrita de conteúdo (formatação Markdown)
* facilidade na colaboração (alterações podem ser feitas diretamente na interface web do GitHub)
* controlo de versões e backup de versões anteriores (pelo uso implícito do git)

### Metadados do site e tema visual

A configuração básica do site encontra-se no ficheiro [_config.yml](https://github.com/waldyrious/rendimentobasico.pt/blob/master/_config.yml).

Este ficheiro define parâmetros usados pelo Jekyll -- nomeadamente, o título e descrição do site, e o estilo visual,
que neste caso é baseado no tema [minimal](https://github.com/pages-themes/minimal) do Github Pages.

### Configuração da estrutura e aparência

Os principais ficheiros que determinam a estrutura e a aparência das páginas são os layouts (templates HTML) e as folhas de estilo CSS.

* Os layouts disponíveis encontram-se na pasta `_layouts`; de momento apenas um é usado, [_layouts/default.html](https://github.com/waldyrious/rendimentobasico.pt/blob/master/_layouts/default.html).

* Os estilos disponíveis encontram-se na pasta `assets/css`. O estilo principal é o [assets/css/style.scss](https://github.com/waldyrious/rendimentobasico.pt/blob/master/assets/css/style.scss)
  As regras de estilos podem ser escritos quem em CSS quem em SCSS.

### Metadados das páginas

O Jekyll [requer](https://help.github.com/articles/configuring-jekyll/#front-matter-is-required)
que todas as páginas em Markdown tenham um bloco de metadados no início, demarcados por três traços:

```markdown
---
title: Título da página
layout: post
---

Esta é uma página que usa o layout "post". Os layouts disponíveis encontram-se na pasta `_layouts`.
```

Estes dados podem ser omitidos, mas os demarcadores devem-se manter:

```
---
---

Esta é uma página sem metadados associados, que usa o layout "default".
```

### Testar alterações localmente

Para a maior parte das alterações, bastará editar os ficheiros diretamente no browser,
usando a interface web do GitHub.

No entanto, alterações mais abrangentes
[podem ser testadas localmente](https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/),
usando ferramentas da linha de comandos.

Os passos para montar o site localmente (instruções para Ubuntu Linux) são os seguintes:

* Instalar o Ruby e os pacotes de desenvolvimento necessários:
  `sudo apt install ruby ruby-dev zlib1g-dev nodejs`
* Instalar o Bundler:
  `sudo gem install bundler`
* Clonar o repositório do site e entrar na pasta:
  `git clone https://github.com/waldyrious/rendimentobasico.pt.git && cd rendimentobasico.pt`
* Instalar o Jekyll e restantes dependências do Github Pages:
  `sudo bundle install`

Estes passos preparatórios só têm que ser corridos uma vez.
A partir de agora, para visualizar o site localmente, basta correr o comando

    jekyll serve

e abrir o endereço `localhost:4000` no browser. Para sair, usa-se o comando `Ctrl+C`.

Alterações aos ficheiros originais (markdown) são automaticamente detectadas e o site atualizado.
Este processo pode demorar alguns segundos.

Em alternativa, pode ser usado o comando `jekyll build`,
que gera o site de forma estática numa pasta chamada `_site`,
que pode ser aberta no browser e navegada normalmente,
sem iniciar um servidor local.
