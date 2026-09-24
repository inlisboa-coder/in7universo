# WebTuga deployment setup

Repository: inlisboa-coder/in7universo
Support ticket: #598432C369672

Confirmed by WebTuga on 2026-09-24:
- Git integration is active by default in cPanel via "Git™ Version Control".
- inmundi.com and geointernacional.com are not yet configured as domains in the hosting account.
- Additional domains can be created from cPanel > Domains > Create a New Domain.
- WebTuga nameservers are required for hosted domains.

Goal:
- Keep the existing inlisboa.com website untouched.
- Use one shared build for INMUNDI and GEO Internacional.
- Deploy INMUNDI to a dedicated document root for inmundi.com.
- Deploy GEO Internacional to a dedicated document root for geointernacional.com.
- Do not deploy anything until the exact document roots are confirmed.

Current status:
1. GitHub repository ready.
2. Branch webtuga-setup ready.
3. .cpanel.yml.example exists but automatic deployment is disabled.
4. WebTuga has been asked to add/confirm inmundi.com and geointernacional.com and provide the exact document roots.
5. Production deployment remains blocked only by domain/document-root configuration.

Architecture:
- One application/content base.
- Domain-aware presentation: INMUNDI and GEO Internacional share data but expose different navigation/branding.
- Production build directory expected: dist/

Safety:
- Never deploy to the primary inlisboa.com document root.
- Never overwrite in7artes.com.
