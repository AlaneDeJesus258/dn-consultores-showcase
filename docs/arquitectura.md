# Arquitectura e decisões técnicas — DN Consultores

## Origem das observações
Análise estática do pacote de código `dn-consultoria-dev.zip`; a execução do ambiente de produção não foi confirmada.

## Estrutura observada
- `src/app`: App Router com páginas `/sobre`, `/servicos`, `/grupo-dn`, `/biblioteca`, `/oportunidades` e páginas dinâmicas `/oportunidades/[slug]`.
- `src/components/home`: secções do website — Hero, Services, Projects, Contact, Stats, CTA, Footer e Navbar.
- `src/app/api/contact/route.ts`: endpoint `POST` que recebe mensagem e utiliza Nodemailer/SMTP.
- `src/app/api/newsletter/route.ts`: rota para subscrição de newsletter.
- `src/app/layout.tsx`: metadados, ícones e componente de consentimento de cookies.
- `src/app/robots.ts` e `src/app/sitemap.ts`: suporte à indexação.

## Notas de engenharia
A aplicação distingue apresentação e rotas de servidor, com configuração SMTP obtida de variáveis de ambiente. A interface utiliza React/Next.js com estilos Tailwind e Framer Motion.

## Pontos para aperfeiçoamento antes de uma demonstração técnica aprofundada
- Rever validação, limitação de pedidos e sanitização de campos recebidos nos endpoints públicos.
- Acrescentar testes automatizados relevantes para formulários e fluxos críticos.
- Documentar ambiente, monitorização e estratégia de deploy sem publicar dados privados.
- Capturar evidências da versão publicada em desktop e mobile, removendo contactos e dados não autorizados.

Este documento não certifica auditoria de segurança nem o funcionamento em produção.
