# Instructions Claude Code - Trading & RL

## Contexte Utilisateur
- **Nom**: Luca
- **Domaine**: Trading algorithmique, Expert Advisors (EA), Reinforcement Learning
- **Objectif**: Passer FTMO avec des agents RL (SAC, PPO)
- **Stack**: Python, MetaTrader 5, Stable-Baselines3, PyTorch, pandas, numpy

---

## INSTRUCTIONS OBLIGATOIRES

### 1. Toujours utiliser les MCP disponibles

Avant de repondre, verifie si un MCP peut aider:

| MCP | Quand l'utiliser |
|-----|------------------|
| `wandb` | Analyser les trainings RL (runs, metriques, hyperparametres) |
| `python` | Executer du code, calculer des stats, analyser des donnees |
| `yfinance` | Donnees financieres en temps reel |
| `wolfram-alpha` | Calculs mathematiques complexes |
| `arxiv` | Rechercher des papers sur RL, trading, ML |
| `exa` | Recherche code et documentation a jour |
| `context7` | Documentation des librairies (SB3, PyTorch, etc.) |
| `memory` | Memoriser les insights importants entre sessions |
| `sequential-thinking` | Problemes complexes necessitant reflexion structuree |
| `git` | Versioning du code |
| `github` | Gestion des repos |
| `filesystem` | Lire/ecrire des fichiers |
| `brave-search` | Recherche web |
| `webresearch` | Recherche web avancee avec screenshots |

### 2. Utiliser les Agents/Skills quand pertinent

Les slash commands disponibles pour de meilleurs resultats:

- `/algo` - Expert trading algorithmique niveau hedge fund
- `/rl-trainer` - Entrainer et optimiser les modeles SAC
- `/data-analyst` - Analyser les performances des backtests
- `/auditor` - Evaluation statistique et stress tests FTMO
- `/ftmo` - Regles FTMO critiques
- `/risk` - Risk management FTMO (4R system, position sizing)
- `/quants` - Analyser modeles RL contre regles FTMO
- `/python` - Implementation Python/RL propre
- `/master` - Controle ultime (Quant x RL x Python)
- `/data` - Validation donnees, features, anti-leak
- `/inspect` - Analyse complete trainings
- `/guide` - Guide institutionnel RL Trading Gold
- `/papers` - Papers academiques essentiels RL Trading
- `/agents` - Details complets des 4 agents + Meta-Agent

### 3. Regles de reponse

1. **Repondre a TOUT** - Ne jamais ignorer une partie de la question
2. **Etre precis** - Donner des reponses concretes, pas vagues
3. **Utiliser les MCPs** - Toujours verifier si un MCP peut enrichir la reponse
4. **Code executable** - Tout code doit etre testable immediatement
5. **Contexte FTMO** - Toujours garder en tete les contraintes FTMO:
   - Max drawdown: 10% (daily 5%)
   - Profit target: 10%
   - Pas de martingale, pas de grid trading risque

### 4. Pour les analyses de training RL

Quand l'utilisateur demande d'analyser un training:

1. Utiliser `wandb` MCP pour recuperer les metriques
2. Analyser: reward curve, loss, entropy, explained variance
3. Detecter: overfitting, reward hacking, instabilite
4. Suggerer: ajustements hyperparametres, architecture, reward shaping
5. Comparer avec les best practices academiques (utiliser `arxiv`)

### 5. Pour le code

1. Toujours utiliser `context7` pour la doc a jour des librairies
2. Utiliser `python` MCP pour tester le code avant de le proposer
3. Suivre les conventions: type hints, docstrings, clean code
4. Penser FTMO: risk management integre dans chaque strategie

---

## Rappels importants

- L'utilisateur travaille sur du trading GOLD (XAUUSD)
- Framework RL: Stable-Baselines3 (SAC principalement)
- Broker: MetaTrader 5
- Challenge: FTMO
- Les donnees doivent etre validees (anti-leak, anti-lookahead bias)
