# Portfolio implementation plan

## Direction

Build a custom, single-page Hugo portfolio instead of adopting a third-party theme.
The site should feel like an engineer's portfolio rather than a reskinned résumé:
strong typography, clear evidence of impact, compact technical depth, and fast paths
to projects and contact details.

## Theme evaluation

| Option | Strength | Trade-off | Decision |
| --- | --- | --- | --- |
| Custom Hugo layout | Complete visual control, no theme dependency, smallest build | More initial design work | Selected |
| Celadon | Current, editorial one-page direction | Young project with limited adoption | Reference only |
| Toha | Mature portfolio feature set | More complexity than this site needs | Not selected |
| Hugo Introduction | Proven single-page structure | Requires theme overrides and a PostCSS toolchain | Not selected |

## Information architecture

1. Hero: positioning statement and primary contact action
2. Impact metrics: AI throughput, migrated media, problem-solving, education
3. Experience: product, AI infrastructure, platform, and frontend work
4. Projects: RaftKV as the lead project, followed by three earlier projects
5. Skills: grouped capabilities instead of a long technology cloud
6. Education and achievements
7. Contact and profile links

## Technical architecture

- Hugo Extended with a custom `layouts/home.html` template
- Portfolio copy stored in `data/portfolio.yaml`
- Plain CSS processed and fingerprinted through Hugo Pipes
- Small progressive-enhancement JavaScript file for color theme and reveal motion
- System fonts only; no third-party runtime requests
- GitHub Actions deployment to GitHub Pages
- Production `baseURL` supplied by the Pages workflow, ready for a future domain

## Delivery phases

### Phase 1 - Foundation

- Scaffold Hugo structure
- Add verified résumé and project content
- Build responsive single-page layout
- Configure GitHub Pages workflow

### Phase 2 - Content polish

- Add a professional headshot if desired
- Link public GoDAM demos, documentation, and articles where appropriate
- Confirm whether a public phone number should be displayed
- Refine project descriptions and add screenshots or diagrams selectively

### Phase 3 - Quality and launch

- Run desktop and mobile visual QA
- Check keyboard navigation, reduced motion, contrast, and outbound links
- Run Lighthouse and correct material issues
- Enable GitHub Pages with GitHub Actions as its source
- Deploy from `main`

### Phase 4 - Custom domain

- Purchase the domain
- Add the domain in GitHub Pages settings
- Configure DNS records and HTTPS
- Update `baseURL`, canonical metadata, and the repository `CNAME`

