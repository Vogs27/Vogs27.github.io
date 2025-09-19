---
layout: project
title: Nome del Progetto
description: Una breve descrizione del progetto che appare nelle liste
technologies: [Python, Flask, PostgreSQL, Docker]
status: attivo # o "archiviato" o "completato"
featured: true # se vuoi che appaia in home page
github_url: https://github.com/username/progetto
demo_url: https://progetto-demo.example.com
start_date: 2024-01-15
end_date: # lascia vuoto se ancora attivo
---

# {{ page.title }}

![Screenshot del progetto](/assets/images/progetti/progetto-screenshot.jpg)

## Panoramica

Descrizione dettagliata del progetto, obiettivi, sfide affrontate e soluzioni implementate.

## Tecnologie Utilizzate

{% for tech in page.technologies %}
- {{ tech }}
{% endfor %}

## Caratteristiche Principali

- Caratteristica 1: descrizione
- Caratteristica 2: descrizione  
- Caratteristica 3: descrizione

## Sfide e Soluzioni

### Sfida 1
Descrivi una sfida importante e come l'hai risolta.

### Sfida 2
Descrivi un'altra sfida e la sua soluzione.

## Risultati

Metriche, feedback ricevuto, obiettivi raggiunti.

## Lezioni Apprese

Cosa hai imparato lavorando a questo progetto.

## Link Utili

{% if page.github_url %}
- [Codice sorgente su GitHub]({{ page.github_url }})
{% endif %}
{% if page.demo_url %}
- [Demo live]({{ page.demo_url }})
{% endif %}

---

**Stato del progetto:** {{ page.status | capitalize }}  
**Periodo:** {{ page.start_date | date: "%B %Y" }}{% if page.end_date %} - {{ page.end_date | date: "%B %Y" }}{% else %} - In corso{% endif %}