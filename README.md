# Colégio Aurora

Site institucional demonstrativo de uma escola fictícia. O projeto apresenta uma experiência editorial e responsiva para famílias e serve como demonstração comercial de um site escolar. **Não representa uma instituição real.**

## Estado do projeto

- Aplicação React com Vite e TypeScript.
- Rotas institucionais implementadas em React Router.
- Tema claro e escuro com preferência salva no navegador.
- Conteúdo, localização, contatos e imagens com caráter demonstrativo.
- Build de produção executado com sucesso.
- Ainda não há backend, banco de dados, CRM ou integração com número oficial de WhatsApp.

## Requisitos

- Node.js e npm compatíveis com as versões de dependências definidas no `package.json`.

## Executar localmente

Instale as dependências e inicie o servidor de desenvolvimento:

```bash
npm install
npm run dev
```

O Vite informa no terminal o endereço local. Para compilar e conferir os tipos TypeScript:

```bash
npm run build
```

Para servir localmente o resultado de `dist/`:

```bash
npm run preview
```

## Rotas

| Rota | Conteúdo |
| --- | --- |
| `/` | Página inicial, apresentação da proposta, segmentos, diferenciais e chamadas para contato |
| `/sobre` | Apresentação institucional demonstrativa, princípios, missão, visão e valores |
| `/ensino` | Educação Infantil, Ensino Fundamental e Ensino Médio |
| `/estrutura` | Ambientes escolares apresentados com imagens ilustrativas |
| `/matriculas` | Etapas demonstrativas, formulário de interesse e perguntas frequentes |
| `/contato` | Canais e localização demonstrativos e formulário de contato |

Rotas desconhecidas exibem uma página de não encontrado com link para o início. Em hospedagens estáticas, configure o fallback de SPA para servir `index.html` nas rotas da aplicação.

## Formulários e WhatsApp

Os formulários validam campos obrigatórios e formato de e-mail no navegador. O telefone recebe máscara e precisa conter DDD. Ao continuar, os campos são usados para preparar uma mensagem pré-preenchida em `wa.me`; o usuário escolhe o destinatário no WhatsApp antes de enviar.

O projeto **não transmite nem armazena** os dados do formulário e não confirma que uma mensagem foi enviada. Não existe número oficial configurado. Para uma instituição real, configure o número de atendimento e revise o texto de privacidade antes de ativar o envio direto. Não solicite nem armazene documentos pessoais de estudantes neste formulário.

## Identidade visual e conteúdo

- **Cores:** azul-marinho, azul vivo e amarelo, com superfícies claras e variações para o tema escuro.
- **Tipografia:** Fraunces nos títulos e Manrope nos textos e controles, carregadas do Google Fonts.
- **Fotografia:** imagens externas do Unsplash, usadas como referências ilustrativas; não são registros do Colégio Aurora. As URLs usam parâmetros de redimensionamento e `auto=format`.
- **Interações:** navegação mobile, alternância de tema, formulário e FAQ nativo com elementos `details`.

Antes de adaptar o projeto para uma escola real, substitua textos, imagens, idades/séries, princípios pedagógicos, contatos, endereço, horários e informações de matrícula por conteúdo aprovado pela instituição.

## SEO e publicação

O documento inicial contém idioma `pt-BR`, descrição, metadados Open Graph e favicon. Os títulos e as descrições são atualizados por rota no cliente. O projeto inclui `public/robots.txt` e `public/sitemap.xml`, mas o sitemap usa `colegioaurora.example`, um domínio reservado para demonstração.

Antes de publicar:

1. Atualize o domínio no sitemap e a referência do sitemap em `robots.txt` para a URL pública absoluta.
2. Defina o domínio canônico e configure canonical e URLs Open Graph apropriadas.
3. Considere pré-renderização ou SSR se SEO por página for requisito de produção; hoje os metadados das rotas são atualizados no cliente.
4. Adicione uma imagem Open Graph aprovada pela instituição, se necessário.
5. Não adicione dados estruturados que apresentem a escola fictícia como organização real ou atribuam a ela endereço e outros dados não confirmados.

As fontes do Google Fonts e as fotografias do Unsplash dependem de serviços externos e de conexão com a internet. Se a publicação exigir maior controle de desempenho, privacidade ou disponibilidade, avalie hospedar fontes e imagens localmente com as licenças adequadas.

## Acessibilidade e responsividade

A interface inclui link para pular ao conteúdo, controles rotulados, foco visível, labels associados aos campos, semântica de títulos, navegação por teclado no FAQ nativo e respeito a `prefers-reduced-motion`. O menu mobile expõe estado expandido e relação com a navegação.

Os estilos reorganizam as seções para telas pequenas e médias, em vez de apenas reduzir os elementos do desktop. A revisão visual registrada foi feita em capturas de 320, 390, 768 e 1440 px. Isso não substitui uma auditoria WCAG completa ou validação em dispositivos e leitores de tela.

## Verificações realizadas

- `npm run build` — concluído com sucesso; executa `tsc -b` e o build de produção do Vite.
- `git diff --check` — concluído sem erros.
- Capturas visuais no Chromium em 320, 390, 768 e 1440 px para revisão de composição e responsividade.

Não foram executados testes automatizados de interação, Lighthouse, axe ou auditoria completa de console/rede. Playwright não estava instalado no projeto no momento da revisão.

## Estrutura principal

```text
src/
  App.tsx       Rotas, conteúdo, componentes e interações
  main.tsx      Inicialização React e BrowserRouter
  styles.css    Identidade visual, layouts e breakpoints
public/
  favicon.svg   Ícone do site
  robots.txt    Regras para crawlers
  sitemap.xml  Sitemap demonstrativo com domínio .example
index.html      Metadados iniciais, fontes e tema antes da renderização
vite.config.ts  Configuração do Vite
```

## Pendências para uma entrega institucional real

- Receber e validar nome, história, proposta pedagógica e conteúdo institucional oficiais.
- Substituir fotos ilustrativas por imagens autorizadas e acessíveis.
- Configurar WhatsApp, telefone, e-mail, endereço, mapa e horários reais.
- Decidir se os formulários devem enviar mensagens diretamente, registrar leads ou integrar CRM; implementar e testar essa integração antes de prometer retorno.
- Atualizar domínio, sitemap, canonical, Open Graph e hospedagem com fallback de SPA.
- Executar testes funcionais completos, revisão de links, auditoria de acessibilidade e medição de Core Web Vitals no ambiente de publicação.

