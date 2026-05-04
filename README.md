# WhatsApp SaaS Meta Skills

Private Codex skills for builders creating a WhatsApp SaaS on top of Meta Embedded Signup, WhatsApp Cloud API, Vercel, and Supabase.

## Included skills

- `whatsapp-meta-app-review`
  Helps prepare a WhatsApp SaaS for Meta App Review approval, using a proven screencast structure, reviewer-facing notes, and rejection remediation patterns.

- `whatsapp-saas-meta-infra`
  Helps implement the technical infrastructure of a WhatsApp SaaS, including Embedded Signup, callback URLs, token exchange, webhooks, Supabase persistence, and deauthorize/data deletion flows.

## Install with npx

Install each skill directly into your local Codex skills folder with `degit`.

### Windows PowerShell

```powershell
npx degit kevinrivm/whatsapp-saas-meta-skills/skills/whatsapp-meta-app-review "$HOME/.codex/skills/whatsapp-meta-app-review"
npx degit kevinrivm/whatsapp-saas-meta-skills/skills/whatsapp-saas-meta-infra "$HOME/.codex/skills/whatsapp-saas-meta-infra"
```

### macOS / Linux

```bash
npx degit kevinrivm/whatsapp-saas-meta-skills/skills/whatsapp-meta-app-review ~/.codex/skills/whatsapp-meta-app-review
npx degit kevinrivm/whatsapp-saas-meta-skills/skills/whatsapp-saas-meta-infra ~/.codex/skills/whatsapp-saas-meta-infra
```

After installation, restart Codex so the new skills are discovered.

## Suggested usage

- Use `$whatsapp-meta-app-review` when working on Meta permission approval, reviewer notes, and App Review screencasts.
- Use `$whatsapp-saas-meta-infra` when building the actual SaaS infrastructure for WhatsApp.
