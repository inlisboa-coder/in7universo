# WebTuga deployment setup

Repository: inlisboa-coder/in7universo

Goal:
- Keep the existing inlisboa.com website untouched.
- Use one shared build for INMUNDI and GEO Internacional.
- Deploy INMUNDI to a dedicated document root for inmundi.com.
- Deploy GEO Internacional to a dedicated document root for geointernacional.com.
- Do not deploy anything until the WebTuga/cPanel document roots are confirmed.

Recommended cPanel flow:
1. cPanel > Files > Git Version Control.
2. Clone the public repository using:
   https://github.com/inlisboa-coder/in7universo.git
3. Use branch webtuga-setup while validating the connection.
4. Confirm the document roots for inmundi.com and geointernacional.com.
5. Only after confirmation, promote .cpanel.yml.example to .cpanel.yml and adjust paths if necessary.

Architecture:
- One application/content base.
- Domain-aware presentation: INMUNDI and GEO Internacional share data but expose different navigation/branding.
- Production build directory expected: dist/

Safety:
- Never deploy to the primary inlisboa.com document root.
- Never overwrite in7artes.com.
