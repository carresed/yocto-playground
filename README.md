# Yocto Playground 🧱

Un ambiente Yocto pre-configurato per GitHub Codespaces.

## Come iniziare

1. Crea un repo su GitHub (es. `yocto-playground`)
2. Pusha questi file sul branch `main`
3. Apri il repo in GitHub Codespaces (basta cliccare `Code` → `Create codespace`)
4. Nella console del Codespace:

```bash
cd poky
source oe-init-build-env ../build
echo 'SSTATE_DIR = "/workspaces/sstate-cache"' >> conf/local.conf
echo 'DL_DIR = "/workspaces/downloads"' >> conf/local.conf
bitbake core-image-minimal
```

La prima build richiede ~1-2 ore (tutto in cache su Codespaces).
Le rebuild successive sono molto più veloci.

## Struttura

```
yocto-playground/
├── .devcontainer/
│   └── devcontainer.json    ← Config Codespaces (Ubuntu + dipendenze Yocto)
├── poky/                     ← Poky reference (clonato nel devcontainer)
├── meta-mio/                 ← Il tuo primo layer personalizzato (da creare dopo)
└── README.md
```
