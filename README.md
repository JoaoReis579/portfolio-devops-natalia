# Portfólio profissional — João Reis

Portfólio pessoal de João Reis, estudante de Análise e Desenvolvimento de Sistemas,
técnico em Desenvolvimento de Sistemas e estagiário na área de banco de dados.

## Acesse

[Ver o portfólio publicado](https://joaoreis579.github.io/portfolio-devops-natalia/)

## Tecnologias

- HTML e CSS
- C, C#, Java, JavaScript e Python
- SQL, Oracle e MongoDB
- GitHub Actions e GitHub Pages

## Estrutura

- `index.html`: conteúdo do portfólio.
- `style.css`: estilos e layout responsivo.
- `img/avatar.svg`: ilustração genérica do perfil.
- `.github/workflows/ci.yml`: validação de HTML e links.
- `.github/workflows/deploy.yml`: publicação no GitHub Pages.

## Desenvolvimento e validação

O projeto foi organizado em etapas, seguindo o fluxo observado no repositório de
referência:

1. Criar a página e personalizar conteúdo, habilidades e projetos.
2. Configurar a integração contínua para validar o HTML.
3. Configurar o deploy automático pelo GitHub Pages.
4. Documentar como executar e publicar o site.
5. Adicionar validação automática de links.

Na cópia personalizada, as validações locais de HTML e links foram executadas com
sucesso após a substituição dos dados e da imagem de perfil.

No repositório de referência, os registros públicos mostram:

| Etapa | CI | Deploy |
| --- | --- | --- |
| Primeira versão do portfólio | Falhou | Falhou |
| Configuração do pipeline de CI | Sucesso | Falhou |
| Configuração do deploy automático | Sucesso | Sucesso |
| Melhoria da documentação | Sucesso | Sucesso |
| Validação de links | Sucesso | Sucesso |

As falhas iniciais foram confirmadas no histórico público de Actions da
[referência](https://github.com/sfvitoriaa/esteira-prod/actions), mas o GitHub não
retornou os jobs nem os logs dessas execuções quando consultados. Por isso, a causa
das falhas não é atribuída aqui. Esses resultados pertencem ao repositório de
referência; não são execuções deste projeto.

### Falhas e correções nesta cópia

1. No primeiro deploy, `Configurar GitHub Pages` retornou `404` porque Pages ainda
   estava desativado. A fonte foi habilitada como **GitHub Actions** nas
   configurações do repositório.
2. Na tentativa seguinte, a configuração e o upload do artefato passaram, mas
   `deploy-pages` informou que não encontrou o artefato `github-pages`. A execução
   seguinte, mesmo com as actions atualizadas para Node.js 24, repetiu esse erro.
3. O workflow foi separado em jobs de build e deploy, com `needs: build` para
   garantir que o artefato estivesse disponível antes da publicação. Na execução
   seguinte, CI e deploy passaram e o site ficou disponível no link acima.

## Executar localmente

Requer Node.js 22 ou superior.

```powershell
npm ci
npx htmlhint index.html
npx linkinator . --recurse
```

Para publicar, envie as alterações para a branch `main` e habilite GitHub Pages
usando GitHub Actions como fonte de publicação.

## Sobre o autor

João Reis — Cataguases, MG.

[GitHub](https://github.com/JoaoReis579)
