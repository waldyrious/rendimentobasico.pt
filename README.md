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

O Jekyll requer que todos as páginas em Markdown tenham um bloco de metadados no início, demarcados por três traços:

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
