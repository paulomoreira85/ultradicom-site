# Ultra DICOM — Site Oficial

Landing page de venda do **Ultra DICOM** (servidor de impressão DICOM).
Estática, sem build step, hospedada na **Vercel** com domínio `ultradicom.com.br`.

## Estrutura

```
ultradicom-site/
├── index.html              página principal
├── obrigado.html           página pós-pagamento (cliente cai aqui após pagar)
├── vercel.json             config de cache, headers e redirects
├── images/
│   ├── logo.svg            logo Ultra DICOM (UD em gradiente azul)
│   ├── app-mockup.svg      mockup da janela principal do app
│   ├── rule-config-mockup.svg  mockup da tela "Rule Configuration"
│   ├── paper-size-mockup.svg   mockup do mapeamento de papéis
│   ├── print-mockup.svg    mockup de folha A4 impressa
│   └── modalities-mockup.svg   mockup das 4 modalidades
├── .gitignore
└── README.md
```

## Stack
- HTML estático puro
- Tailwind CSS via CDN (zero build)
- Fonts: Inter + Plus Jakarta Sans (Google Fonts)
- Hospedado: Vercel (gratuito)
- Domínio: ultradicom.com.br
- Download do .exe: GitHub Releases deste repo

## Como editar

Edite `index.html` ou `obrigado.html` em qualquer editor de texto.
Para visualizar localmente, basta dar duplo clique em `index.html` — abre no navegador.

## Deploy

### Pré-requisitos
- Conta no [GitHub](https://github.com) (já tem: `PauloMoreira85`)
- Conta na [Vercel](https://vercel.com) (login com GitHub)
- Domínio `ultradicom.com.br` (já registrado)

### Deploy inicial (uma vez só)

```bash
# 1. Inicializar repositório
cd C:\Projetos\ultradicom-site
git init
git add .
git commit -m "Initial commit — Ultra DICOM landing"

# 2. Criar repo no GitHub (via gh CLI ou manual em github.com/new)
gh repo create PauloMoreira85/ultradicom-site --public --source=. --remote=origin --push

# 3. Conectar Vercel
# - Acesse vercel.com → "Add New Project"
# - Importe o repositório PauloMoreira85/ultradicom-site
# - Framework: "Other" (estático)
# - Root: ./ (raiz)
# - Build Command: deixar vazio
# - Output Directory: deixar vazio
# - Deploy

# 4. Apontar domínio
# - Painel Vercel → Settings → Domains → Add ultradicom.com.br
# - Adicione o registro DNS na Registro.br conforme orientação da Vercel
```

### Atualizações futuras

Após mudanças no código:

```bash
git add .
git commit -m "Atualização: descrição"
git push
```

Vercel publica automaticamente em ~30 segundos.

## Atualizar o .exe pra download (GitHub Releases)

Quando quiser atualizar o `Ultra_Dicom.exe` que o site oferece pra download:

1. No projeto Ultra_Dicom, gere o exe novo: `powershell -ExecutionPolicy Bypass -File build-release.ps1 -Version 1.x.x`
2. Vá em `https://github.com/PauloMoreira85/ultradicom-site/releases/new`
3. Tag: `v1.x.x` (ex: `v1.1.3`)
4. Title: `Ultra DICOM v1.x.x`
5. Anexe o **`Ultra_Dicom.exe`** (que está em `C:\Projetos\Ultra_Dicom\dist\Ultra_Dicom_v1.x.x\` após extrair o zip)
6. Marca "Latest release"
7. Publish

O link do site (`/baixar` ou botão direto) sempre aponta para `releases/latest/download/Ultra_Dicom.exe` — pega automaticamente a versão mais nova.

## Placeholders a substituir

Antes de publicar, troque nos arquivos:

| Placeholder | Onde aparece | Substituir por |
|---|---|---|
| `SEU_NUMERO_AQUI` | `index.html`, `obrigado.html` | Número WhatsApp formato `5544999999999` |
| `https://pagamento.ultradicom.com.br` | `index.html` | Link de pagamento real (Asaas/MP/etc) |

Use Find & Replace global no editor para trocar todas as ocorrências de uma vez.

## Suporte

Email: suporte@ultradicom.com.br
