# Bookivox Docs

Documentation officielle de Bookivox basee sur `Mintlify`.

Ce repo regroupe :
- la documentation produit
- la reference API
- les guides de deploiement
- les guides developpeur
- les captures et assets de doc

## Structure

```text
bookivox-docs/
├── api-reference/
├── configurations/
├── core-concepts/
├── deployment/
├── developer/
├── getting-started/
├── integrations/
├── images/
├── sdks/
├── voice-agent/
├── docs.json
└── custom.css
```

## Responsabilites

- documenter le produit et ses usages
- exposer la reference API publique
- decrire le deploiement et les integrations
- accompagner les utilisateurs et les developpeurs

## Hors perimetre

Ce repo ne contient pas :
- le dashboard Next.js
- le runtime backend FastAPI

## Repos relies

- `bookivox-api` : source de verite OpenAPI
- `bookivox-ui` : surfaces produit documentees

## Lancement local

```bash
npm i -g mint
mint dev
```
