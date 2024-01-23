---
title: Home
layout: home
---

# YAML

## 1.1. Descripció del llenguatge

**YAML** és un format de serialització de dades inspirat en diverses llenguatges com XML, C i Python. Va ser creat per Clark Evans en el 2001 sota l’acrònim "Yet Another Markup Language.", posteriorment va canviar a "YAML Ain't Markup Language." Va ser dissenyat per què sigui fàcil de llegir i escriure.

### Característiques clau del llenguatge YAML
Com hem dit abans, va ser dissenyat per ser fàcilment llegible pels humans, per això utilitza sagnat i espais en blanc de manera significativa per representar l’estructura jeràrquica de les dades. Utilitza una notació basada en el sagnat fent servir a vegades un conjunt de caràcters Sigil. També admet diversos tipus de dades com cadenes de text, números, llistes i diccionaris. A més permet la representació de dades complexes i anidades. Va ser concebut amb la convicció que totes les dades poden ser representades de manera idònia mitjançant combinacions de llistes, hash i dades escalars (valors senzills). I, per últim, també és extensible, vol dir que pot adaptar-se per satisfer les necessitats específiques de diferents aplicacions o entorns.

### Usos més habituals
**YAML** s’utilitza per la configuració d’aplicacions i serveis, eines d’orquestació com Asible, emmagatzematge de dades estructurades, representació de fluxos de treball. 

## 1.2. Possibilitats

En aplicacions web s'utilitza per emmagatzemar informació de configuració i connexió a bases de dades. Destaca per la seva capacitat de representar dades complexes com llistes i diccionaris. També és molt utilitzat en la definició de fluxos de treball per a la integració i desplegament continu en eines com GitHub Actions i GitLab CI/CD, simplificant la gestió de processos automatitzats. És una elecció comuna en el camp de l'automatització i orquestració on s'utilitza per definir tasques i configuracions en entorns com Ansible i Kubernetes, proporcionant una manera clara i llegible de descriure les operacions automatitzades en infraestructures complexes.

Com hem explicat en el punt 1.1, el llenguatge **YAML** funciona mitjançant l'ús d'indentació i caràcters especials que defineixen la seva estructura. Utilitzen una sintaxi clara i fàcil d'entendre, amb l'ús d'espais en blanc i caràcters com: els dos punts, guions i claudàtors. Aquí mostrem diferents representacions dels tipus de dades utilitzant **YAML**:

## Valors Simples 

### Cadenes de Caràcters:
```yaml
nom: Sergi
missatge: "Aixo es un string"
```

### Nombres :
```yaml
edat: 25
preu: 19.99
```

### Booleans:
```yaml
actiu: true
completat: false
```

### Nuls:
```yaml
opcional: ~
```

### Llistes 
```yaml
colors:
  - vermell
  - verd
  - blau
tasques:
  - Terminar aquesta pràctica
  - Fer exercici
  - Estudiar
```

### Mapejos
```yaml
persona:
  nom: Sergi
  edat: 23
  adreça:
    carrer: Carrer 1
    ciutat: Barcelona
llibre:
  títol: "El Quixot"
  autor: Miguel de Cervantes
```

### Valors Etiquetats
```yaml
edat: !!int 25
preu: !!float 19.99
```






This is a *bare-minimum* template to create a Jekyll site that uses the [Just the Docs] theme. You can easily set the created site to be published on [GitHub Pages] – the [README] file explains how to do that, along with other details.

If [Jekyll] is installed on your computer, you can also build and preview the created site *locally*. This lets you test changes before committing them, and avoids waiting for GitHub Pages.[^1] And you will be able to deploy your local build to a different platform than GitHub Pages.

More specifically, the created site:

- uses a gem-based approach, i.e. uses a `Gemfile` and loads the `just-the-docs` gem
- uses the [GitHub Pages / Actions workflow] to build and publish the site on GitHub Pages

Other than that, you're free to customize sites that you create with this template, however you like. You can easily change the versions of `just-the-docs` and Jekyll it uses, as well as adding further plugins.

[Browse our documentation][Just the Docs] to learn more about how to use this theme.

To get started with creating a site, simply:

1. click "[use this template]" to create a GitHub repository
2. go to Settings > Pages > Build and deployment > Source, and select GitHub Actions

If you want to maintain your docs in the `docs` directory of an existing project repo, see [Hosting your docs from an existing project repo](https://github.com/just-the-docs/just-the-docs-template/blob/main/README.md#hosting-your-docs-from-an-existing-project-repo) in the template README.

----

[^1]: [It can take up to 10 minutes for changes to your site to publish after you push the changes to GitHub](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll#creating-your-site).

[Just the Docs]: https://just-the-docs.github.io/just-the-docs/
[GitHub Pages]: https://docs.github.com/en/pages
[README]: https://github.com/just-the-docs/just-the-docs-template/blob/main/README.md
[Jekyll]: https://jekyllrb.com
[GitHub Pages / Actions workflow]: https://github.blog/changelog/2022-07-27-github-pages-custom-github-actions-workflows-beta/
[use this template]: https://github.com/just-the-docs/just-the-docs-template/generate
