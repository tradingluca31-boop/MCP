# Guide d'Installation MCP pour Claude Code VSCode

> **INSTRUCTIONS POUR CLAUDE CODE** : Si tu lis ce fichier, tu dois aider l'utilisateur a installer tous les 16 MCP servers listes ci-dessous. Suis les etapes dans l'ordre et verifie chaque installation. Adapte les chemins selon le nom d'utilisateur Windows de l'utilisateur.

---

## Pour Claude Code : Comment utiliser ce guide

1. **Lis ce fichier en entier**
2. **Demande a l'utilisateur** son nom d'utilisateur Windows (remplace `%USERNAME%`)
3. **Execute les commandes** une par une dans Anaconda Prompt ou aide l'utilisateur a les executer
4. **Configure le fichier `.claude.json`** avec les bonnes cles API
5. **Verifie** que tous les MCP sont "connected" (vert)

---

## Prerequis

### 1. Installer Anaconda (ou Python + Node.js)
- Telecharger : https://www.anaconda.com/download
- Installer avec l'option "Add to PATH"

### 2. Installer Node.js via Anaconda
```bash
conda install -c conda-forge nodejs
```

### 3. Verifier les installations
```bash
node --version
npm --version
python --version
```

---

## Installation des MCP (dans Anaconda Prompt)

### Etape 1 : MCP npm (installation globale)
```bash
npm install -g @modelcontextprotocol/server-github
npm install -g @modelcontextprotocol/server-filesystem
npm install -g @modelcontextprotocol/server-brave-search
npm install -g @mseep/git-mcp-server
npm install -g @modelcontextprotocol/server-sequential-thinking
npm install -g @modelcontextprotocol/server-memory
npm install -g mcp-server-webresearch
npm install -g yfinance-mcp-server
npm install -g @modelcontextprotocol/server-everything
npm install -g @anthropics/context7-mcp
npm install -g exa-mcp-server
```

### Etape 2 : Wolfram Alpha MCP (clone GitHub)
```bash
cd C:\Users\%USERNAME%
git clone https://github.com/emcie-co/wolframalpha-llm-mcp.git
cd wolframalpha-llm-mcp
npm install
npm run build
```

### Etape 3 : ArXiv MCP (clone GitHub)
```bash
cd C:\Users\%USERNAME%
git clone https://github.com/blazickjp/arxiv-mcp-server.git
cd arxiv-mcp-server
npm install
npx tsc
```

### Etape 4 : Python Interpreter MCP
```bash
pip install uv
cd C:\Users\%USERNAME%
git clone https://github.com/punkpeye/mcp-python-interpreter.git
cd mcp-python-interpreter
uv sync
```

### Etape 5 : W&B (Weights & Biases) MCP
```bash
cd C:\Users\%USERNAME%
git clone https://github.com/tsilva/simple-wandb-mcp-server.git
cd simple-wandb-mcp-server
pip install wandb matplotlib mcp python-dotenv httpx
```

### Etape 6 : ChessAgine MCP
```bash
npx -y @smithery/cli install @jalpp/chessagine-mcp --client claude
```
> Note: Appuyer sur Entree pour passer les options optionnelles (Lichess API, username, etc.)

---

## Cles API necessaires

> **Claude Code** : Demande a l'utilisateur ses cles API pour chaque service, ou aide-le a les creer.

| Service | URL pour obtenir la cle |
|---------|------------------------|
| GitHub | https://github.com/settings/tokens |
| Brave Search | https://brave.com/search/api/ |
| Wolfram Alpha | https://developer.wolframalpha.com/ |
| Exa | https://exa.ai/ |
| W&B | https://wandb.ai/authorize |

---

## Configuration .claude.json

> **Claude Code** : Cree ou modifie le fichier `C:\Users\%USERNAME%\.claude.json` avec cette configuration. Remplace `%USERNAME%` par le vrai nom d'utilisateur et les cles API par celles de l'utilisateur.

```json
{
  "mcpServers": {
    "github": {
      "type": "stdio",
      "command": "C:\\Users\\%USERNAME%\\anaconda3\\mcp-server-github.cmd",
      "args": [],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "VOTRE_TOKEN_GITHUB"
      }
    },
    "filesystem": {
      "type": "stdio",
      "command": "C:\\Users\\%USERNAME%\\anaconda3\\mcp-server-filesystem.cmd",
      "args": [
        "C:\\Users\\%USERNAME%"
      ]
    },
    "brave-search": {
      "type": "stdio",
      "command": "C:\\Users\\%USERNAME%\\anaconda3\\mcp-server-brave-search.cmd",
      "args": [],
      "env": {
        "BRAVE_API_KEY": "VOTRE_CLE_BRAVE"
      }
    },
    "git": {
      "type": "stdio",
      "command": "C:\\Users\\%USERNAME%\\anaconda3\\git-mcp-server.cmd",
      "args": []
    },
    "sequential-thinking": {
      "type": "stdio",
      "command": "C:\\Users\\%USERNAME%\\anaconda3\\mcp-server-sequential-thinking.cmd",
      "args": []
    },
    "wolfram-alpha": {
      "type": "stdio",
      "command": "C:\\Users\\%USERNAME%\\anaconda3\\node.exe",
      "args": [
        "C:\\Users\\%USERNAME%\\wolframalpha-llm-mcp\\build\\index.js"
      ],
      "env": {
        "WOLFRAM_LLM_APP_ID": "VOTRE_APP_ID_WOLFRAM"
      }
    },
    "memory": {
      "type": "stdio",
      "command": "C:\\Users\\%USERNAME%\\anaconda3\\mcp-server-memory.cmd",
      "args": []
    },
    "webresearch": {
      "type": "stdio",
      "command": "C:\\Users\\%USERNAME%\\anaconda3\\mcp-server-webresearch.cmd",
      "args": []
    },
    "arxiv": {
      "type": "stdio",
      "command": "C:\\Users\\%USERNAME%\\anaconda3\\node.exe",
      "args": [
        "C:\\Users\\%USERNAME%\\arxiv-mcp-server\\dist\\index.js"
      ]
    },
    "yfinance": {
      "type": "stdio",
      "command": "C:\\Users\\%USERNAME%\\anaconda3\\yfinance-mcp-server.cmd",
      "args": []
    },
    "everything": {
      "type": "stdio",
      "command": "C:\\Users\\%USERNAME%\\anaconda3\\mcp-server-everything.cmd",
      "args": []
    },
    "context7": {
      "type": "stdio",
      "command": "C:\\Users\\%USERNAME%\\anaconda3\\context7-mcp.cmd",
      "args": []
    },
    "exa": {
      "type": "stdio",
      "command": "C:\\Users\\%USERNAME%\\anaconda3\\node.exe",
      "args": [
        "C:\\Users\\%USERNAME%\\anaconda3\\node_modules\\exa-mcp-server\\.smithery\\stdio\\index.cjs"
      ],
      "env": {
        "EXA_API_KEY": "VOTRE_CLE_EXA"
      }
    },
    "python": {
      "type": "stdio",
      "command": "C:\\Users\\%USERNAME%\\mcp-python-interpreter\\.venv\\Scripts\\mcp-python-interpreter.exe",
      "args": [
        "--dir",
        "C:\\Users\\%USERNAME%"
      ]
    },
    "wandb": {
      "type": "stdio",
      "command": "C:\\Users\\%USERNAME%\\anaconda3\\python.exe",
      "args": [
        "C:\\Users\\%USERNAME%\\simple-wandb-mcp-server\\server.py"
      ],
      "env": {
        "WANDB_API_KEY": "VOTRE_CLE_WANDB"
      }
    },
    "chessagine-mcp": {
      "type": "stdio",
      "command": "C:\\Users\\%USERNAME%\\anaconda3\\npx.cmd",
      "args": [
        "-y",
        "mcp-remote",
        "https://server.smithery.ai/@jalpp/chessagine-mcp/mcp"
      ]
    }
  }
}
```

---

## Liste des 16 MCP

| # | MCP | Description |
|---|-----|-------------|
| 1 | github | Gestion repos, PRs, issues |
| 2 | filesystem | Acces fichiers locaux |
| 3 | brave-search | Recherche web |
| 4 | git | Versioning et commits |
| 5 | sequential-thinking | Raisonnement structure |
| 6 | wolfram-alpha | Calculs maths/science |
| 7 | memory | Memoire persistante |
| 8 | webresearch | Web + screenshots |
| 9 | arxiv | Papers academiques |
| 10 | yfinance | Donnees financieres |
| 11 | everything | Test MCP |
| 12 | context7 | Documentation librairies |
| 13 | exa | Recherche IA avancee |
| 14 | python | Execution code Python |
| 15 | wandb | Suivi training RL |
| 16 | chessagine-mcp | Echecs (Stockfish, puzzles) |

---

## Verification finale

> **Claude Code** : Apres installation, demande a l'utilisateur de redemarrer VSCode et verifie que tous les MCP sont "connected" (vert) dans les parametres de l'extension Claude.

---

## Fichier CLAUDE.md

> **Claude Code** : Copie aussi le fichier `CLAUDE.md` de ce repo dans `C:\Users\%USERNAME%\CLAUDE.md` pour avoir les instructions personnalisees pour le trading et RL.

---

## Troubleshooting

Si un MCP echoue ("failed" en rouge):

1. **Verifier le chemin** - Le nom d'utilisateur est-il correct ?
2. **Verifier l'installation** - Le package npm/git clone a-t-il fonctionne ?
3. **Verifier les cles API** - La cle est-elle valide ?
4. **Redemarrer VSCode** - Parfois necessaire apres modification du .claude.json

---

## Contexte utilisateur

L'utilisateur (Luca) travaille sur :
- Trading algorithmique GOLD (XAUUSD)
- Reinforcement Learning (SAC, PPO) avec Stable-Baselines3
- Expert Advisors (EA) pour MetaTrader 5
- Challenge FTMO
