# Limpeza de URLs Antigas - CloudData Site de Manutenção

## Problema
O Google Safe Browsing marcou o site como "perigoso" devido a:
- URLs antigas do WordPress ainda indexadas
- Possíveis redirects suspeitos do site antigo
- Conteúdo legado acessível

## Solução Implementada

### 1. Bloqueio de URLs Antigas (HTTP 410 Gone)
Todas as URLs antigas do WordPress retornam **410 Gone** (recurso removido permanentemente):

- `/wp-admin/*` - Painel administrativo WordPress
- `/wp-content/*` - Arquivos de conteúdo WordPress
- `/wp-includes/*` - Arquivos core WordPress
- `/wp-login.php` - Página de login
- `/xmlrpc.php` - XML-RPC (frequentemente explorado)
- `/*.php` - Todos os arquivos PHP
- `/uploads/*` - Diretório de uploads
- `/blog/*` - Posts antigos
- `/categoria/*` - Categorias em português
- `/category/*` - Categorias em inglês
- `/author/*` - Páginas de autor
- `/tag/*` - Páginas de tags

### 2. Redirecionamento Limpo
Qualquer outra URL (`/*`) redireciona para a página limpa de manutenção (`/index.html`)

### 3. Bloqueio no robots.txt
Crawlers são instruídos a não indexar URLs antigas

### 4. Página 100% Limpa
- ❌ Sem scripts externos
- ❌ Sem links externos (exceto LinkedIn no Schema.org)
- ❌ Sem iframes
- ❌ Sem redirects JavaScript
- ✅ Apenas HTML/CSS inline puro
- ✅ Schema.org para dados estruturados
- ✅ Headers de segurança HTTP

## Próximos Passos

1. **Deploy imediato** dos arquivos atualizados
2. **Solicitar revisão ao Google** após 24h do deploy
3. **Monitorar** o Google Search Console para verificar se as URLs antigas foram removidas do índice
4. **Aguardar** 2-7 dias para o Google recrawlear e remover o alerta

## Arquivos Modificados

- `index.html` - Página de manutenção limpa
- `staticwebapp.config.json` - Configuração de rotas e status codes
- `robots.txt` - Bloqueio de crawlers em URLs antigas
- `sitemap.xml` - Apenas URL raiz
- `security.txt` - Informações de segurança

## Data de Implementação
15 de Janeiro de 2026
