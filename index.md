---
title: Pràctica YAML Markdown
layout: home
---

# [YAML](#yaml)

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

## 1.3. Exemples de diferents possibilitats del llenguatge

### Configuració d'Aplicacions Web i Connexió a Bases de Dades:
```yaml
servidor:
  port: 8080
  host: exemple.cat
base_dades:
  nom: principal
  usuari: usuari1
  contrasenya: password
```

### Representació de Dades Complexes:
```yaml
  - nom: Joan
    edat: 28
    tasques:
      - nom: Feina A
        completat: cert
      - nom: Feina B
        completat: fals
  - nom: Maria
    edat: 24
    tasques:
      - nom: Feina C
        completat: cert
      - nom: Feina D
        completat: cert
```

### Definició de Flujos de Treball (CI/CD) amb GitHub Actions:
```yaml
name: GitHub Actions Demo
run-name: ${{ github.actor }} is testing out GitHub Actions 🚀
on: [push]
jobs:
  Explore-GitHub-Actions:
    runs-on: ubuntu-latest
    steps:
      - run: echo "🎉 The job was automatically triggered by a ${{ github.event_name }} event."
      - run: echo "🐧 This job is now running on a ${{ runner.os }} server hosted by GitHub!"
      - run: echo "🔎 The name of your branch is ${{ github.ref }} and your repository is ${{ github.repository }}."
      - name: Check out repository code
        uses: actions/checkout@v4
      - run: echo "💡 The ${{ github.repository }} repository has been cloned to the runner."
      - run: echo "🖥️ The workflow is now ready to test your code on the runner."
      - name: List files in the repository
        run: |
          ls ${{ github.workspace }}
      - run: echo "🍏 This job's status is ${{ job.status }}."
```

### Automatització i Orquestració amb Ansible
```yaml
---
- hosts: all
  vars:
    storage_volumes:
      - name: barefs
        type: disk
        disks:
          - sdb
        fs_type: xfs
        mount_point: /mnt/data
  roles:
    - rhel-system-roles.storage
```

### Automatització amb Kubernetes:
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 3
  selector:
    matchLabels:
      app: app
  template:
    metadata:
      labels:
        app: app
    spec:
      containers:
      - name: app-container
        image: app-image:latest
        ports:
        - containerPort: 80
```

Un exemple de la documentació de Google [App Engine].

## 1.4. Validació dels exemples

Per realitzar la validació d'un fitxer YAML faria servir un eina local si es tractés de dades sensibles com poden ser contrasenyes en text clar o detalls de la base de dades. En aquest cas farem servir yamllint. Tenim altres opcions local com podria ser visual studio amb la seva extensió corresponent.

Cal mencionar que podem fer servir alguna utilitat web, sense poder garantir les nostres dades: [Yamllint en versió web].

Tot i que hi han eines per validar haurem de seguir la documentació sempre que es tracti de configuracions o definició d’estructures, el nostre fitxer por estar ven redactat de cara a un validador pero si la aplicació espera un altra cosa mai funcionara.
YAMLlint funciona de la següent manera:
Examina l’arxiu YAML per assegurar-se que compleix amb la sintaxi i estructures correctes segons les especificacions de YAML. Verifica que la indentació, els dos punts (per separar claus) i els valors estiguin correctes.
A part de la sintaxis, YAMLlint també es preocupa per l’estil del codi YAML. Avalua si l'arxiu segueix convencions d’estil com: l’ús de cometes al voltant de les cadenes, l'alineació de les estructures i altres aspectes que poden afectar la llegibilitat i consistència del codi YAML.
Identifica possibles errors o problemes en l’arxiu YAML que podrien provocar comportaments inesperats o errors d’interpretació: claus duplicades, valors no vàlids…
Proporciona missatges d’error informatius i suggerències de com corregir-ho. 

## 1.5. Comparació amb XML / DTD - XSD

La principal diferència entre XML i YAML es com representen i estructuren la informació. XML utilitza una sintaxi més detallada amb etiquetes d'obertura i tancament, sovint acompanyada de sistemes de validació. En canvi, YAML utilitza una sintaxi més senzilla i llegible, eliminant la necessitat d'etiquetes addicionals i sense requerir validacions tan formals. La elecció depèn de les preferències específiques: 

XML és més adequat quan es prioritza la validació de les dades, mentre que YAML destaca en situacions on es valora la simplicitat i la llegibilitat.

| YAML                                        | 
|---------------------------------------------|
```yaml
servidor:
  port: 8080
  host: exemple.com
base_dades:
  nom: principal
  usuari: usuari1
  contrasenya: secret123
```

| XML                                         |
|---------------------------------------------|
```xml
<servidor>
  <port>8080</port>
  <host>exemple.com</host>
</servidor>
<base_dades>
  <nom>principal</nom>
  <usuari>usuari1</usuari>
  <contrasenya>secret123</contrasenya>
</base_dades>
```

# Markdown

## 1.1. Descripció del llenguatge

Markdown és un llenguatge de marques lleuger que s'utilitza habitualment per formatar
el text de manera fàcil i ràpida. John Gruber i Aaron Swartz el van crear l'any 2004 
com a llenguatge de marques amb l'objectiu principal de ser fàcil de llegir i escriure 
sense requerir l'ús d'eines complexes. Amb aquest objectiu en ment, també pretenc 
permetre que la gent escrigui en un format de text que sigui fàcil de llegir, fàcil 
d'escriure i convertir documents en HTML vàlid.

Markdown es va inspirar en llenguatges preexistents com setext (1992), Textile (2002) 
i reStructuredTest (2002).

## Usos més habituals

Markdown s'utilitza àmpliament per escriure documents tècnics i d'altres tipus on 
l'estructura i la llegibilitat són importants. Moltes plataformes i fòrums de blocs 
admeten l'escriptura a Markdown, cosa que permet als usuaris formatar fàcilment les 
seves publicacions. Alguns clients de correu electrònic us permeten utilitzar Markdown 
per formatar text i crear ràpidament llistes per redactar correus electrònics. Els 
desenvolupadors utilitzen Markdown per escriure fitxers README als dipòsits de codi 
font en plataformes com GitHub.

## Àmbit

Markdown s’utilitza per a moltes coses, des del desenvolupament de programari fins a 
la creació de contingut en línia. Les plataformes de col·laboració i comunicació com 
Discord admeten l'escriptura en Markdown per facilitar la creació de missatges amb 
format. La seva senzillesa i versatilitat el fan adequat per a qualsevol situació en 
què necessiteu formatar text de manera ràpida i senzilla. A més, moltes plataformes de 
blocs i sistemes de gestió de contingut (CMS) (com WordPress i Ghost) admeten 
l'escriptura a Markdown, proporcionant una manera més eficient d'escriure contingut.

# 2.2. Possibilitats

Com hem vist a l’apartat 2.1, Markdown és un llenguatge de marcat lleuger que utilitza 
una sintaxi senzilla per donar format al text d’una manera ràpida i fàcil. Ara es 
detallen les principals possibilitats de Markdown, incloent el seu funcionament i 
etiquetes.

Encapçalaments: S’utilitzen per estructurar el contingut. Quan més alt és el número de 
l’encapçalament, més petit serà.



----

[App Engine]:https://cloud.google.com/appengine/docs/standard/go111/config/appref?hl=es-419
[Yamllint en versió web]:https://www.yamllint.com/
