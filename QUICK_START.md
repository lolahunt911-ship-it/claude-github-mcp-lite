# Démarrage rapide (3 min)

## Android / Termux

```bash
# 1. Installe Node
pkg update && pkg install nodejs npm git

# 2. Clone le repo
git clone https://github.com/lolahunt911-ship-it/claude-github-mcp-lite
cd claude-github-mcp-lite

# 3. Installe les dépendances
npm install

# 4. Crée .env
cat > .env << EOF
GITHUB_TOKEN=ghp_ton_token_ici
EOF

# 5. Lance
npm start
```

## Obtenir le token (5 min)

1. Ouvre https://github.com/settings/tokens sur ton téléphone
2. Login GitHub
3. "Generate new token (classic)"
4. Nom: `claude-mcp`
5. Coche: `repo` et `issues`
6. "Generate token"
7. Copy le code (commence par `ghp_`)
8. Colle-le dans `.env`

## Test

Si tu vois `✅ GitHub MCP Server OK`, c'est bon.

Ctrl+C pour arrêter.

## Utiliser dans Claude

Sur ton desktop / laptop:

1. Télécharge Claude Desktop
2. Ouvre config: `~/.config/Claude/claude_desktop_config.json`
3. Ajoute:

```json
{
  "mcpServers": {
    "github": {
      "command": "node",
      "args": ["/home/username/claude-github-mcp-lite/server.js"],
      "env": {
        "GITHUB_TOKEN": "ghp_xxxxx"
      }
    }
  }
}
```

4. Redémarre Claude
5. Demande: "Liste mes repos GitHub"

## Voilà !

C'est tout. Pas de config complexe. Juste Node + GitHub token.
