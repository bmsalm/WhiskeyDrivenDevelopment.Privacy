# Whiskey Driven Development privacy page

One static HTML page for Bobo's White Noise Machine. No build step, package
manager, JavaScript, analytics or embedded payment content is required.

## Current status

- Repository is public; changes are reviewed through PRs to main.
- Initial page is ready for owner review; it has not been approved or published.
- Owner-provided privacy contact: whiskeydrivendevelopment@gmail.com.
- GitHub Pages is not enabled and no domain or DNS record has been configured.
- Intended custom URL: https://privacy.whiskeydrivendevelopment.com/
  (not currently verified or claimed to be live).
- This is not a complete Google Play compliance certification. Final wording
  must match the approved shipping app, in-app notice and Play declarations.

## Publish after approval

1. Review index.html against the actual release candidate, including its
   owner-provided privacy contact, and approve the wording before publication.
2. Merge the reviewed PR with owner authorization.
3. In repository Settings > Pages, choose Deploy from a branch, main, /(root).
   The default URL is https://bmsalm.github.io/WhiskeyDrivenDevelopment.Privacy/.
4. Verify domain ownership in GitHub account Settings > Pages using GitHub's
   supplied TXT record. In this repository's Pages settings, configure
   privacy.whiskeydrivendevelopment.com BEFORE adding the GoDaddy CNAME.
   If GitHub commits a CNAME file directly, preserve/pull that platform change.
5. In GoDaddy DNS for whiskeydrivendevelopment.com, add only this record:

   | Type | Name | Value |
   | --- | --- | --- |
   | CNAME | privacy | bmsalm.github.io |

   Do not include https:// or a repository path in the value. If a privacy record
   already exists, inspect it before replacing anything. Do not change apex, www,
   MX/email or nameservers. Do not create wildcard records or masked forwarding.
6. Wait for DNS/certificate provisioning (GitHub advises up to 24 hours), then
   enable Enforce HTTPS. Verify the page anonymously on a phone and computer,
   its email link, title/contact, and absence of geographic/login restrictions.
7. Add the verified HTTPS URL to Play Console and synchronize the app's offline
   policy/contact through a separate app PR. Complete the other Play declarations.

The domain stays registered with GoDaddy. GitHub Pages hosting and custom-domain
HTTPS are available free for public repositories; domain renewal remains separate.
Do not remove a Pages site while leaving its custom-domain DNS dangling: remove
the associated DNS record when retiring hosting to avoid takeover risk.

## Local review

Open index.html directly in a browser. The page works without a dev server.

Official setup/policy references:
- https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site
- https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages
- https://docs.github.com/en/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https
- https://support.google.com/googleplay/android-developer/answer/10144311
