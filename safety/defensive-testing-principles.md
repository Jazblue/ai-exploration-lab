# Defensive testing principles

The lab may explore cybersecurity and website security, but all tests must be authorised and proportionate.

- Test only systems the operator owns or has explicit permission to assess.
- Start with passive inspection and read-only requests.
- Confirm real pages, routes, scripts, forms and services before testing them.
- Do not invent endpoints or assume a login/contact feature exists.
- Avoid denial-of-service, brute-force, destructive actions, persistence, malware, credential theft or data exfiltration.
- Do not publish secrets, tokens, private IPs, credentials or personal data.
- Treat model-generated findings as hypotheses until independently verified.
- Record scope, method, evidence, impact, limitations and cleanup where applicable.

A less restrictive model is not a substitute for professional judgement, permission or safe testing practice.
