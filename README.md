# CloudData - Site de Manutenção

Página temporária de manutenção para www.clouddata.com.vc

## Estrutura do Projeto

```
├── 18 1.png                      # Logo da empresa
├── ico-clouddata-02.ico          # Favicon
├── index.html                    # Página principal de manutenção
├── staticwebapp.config.json      # Configuração do Azure Static Web App
├── sitemap.xml                   # Sitemap para Google
├── robots.txt                    # Instruções para crawlers
├── security.txt                  # Informações de segurança
└── CLEANUP-DOCS.md               # Documentação da limpeza de URLs antigas
```

## Deploy

Este site está configurado para deploy automático via GitHub Actions no Azure Static Web App.

### Deploy Manual

```bash
az staticwebapp upload \
  --name <nome-do-static-web-app> \
  --resource-group <resource-group> \
  --source .
```

## Características

- ✅ 100% HTML/CSS puro (sem JavaScript)
- ✅ Sem links externos
- ✅ Headers de segurança configurados
- ✅ URLs antigas do WordPress bloqueadas (HTTP 410)
- ✅ Schema.org para dados estruturados
- ✅ Responsivo (desktop, tablet, mobile)

## Segurança

O site implementa as seguintes medidas de segurança:

- X-Content-Type-Options: nosniff
- X-Frame-Options: DENY
- X-XSS-Protection: 1; mode=block
- Strict-Transport-Security (HSTS)
- Content-Security-Policy

## Contato

**CloudData - Soluções em Tecnologia da Informação**

📧 E-mail: suporte@clouddata.com.vc  
📞 Telefones: (11) 4805-4490 / (11) 3995-8370
