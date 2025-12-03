# **Referrer Firewall Test**

This page is for testing our new referrer based firewall rule.
GitHub reliably sends a referrer when you click outbound links, so it is the most stable way to verify the behavior.

---

## **1. Check your current referrer**

Click the link below to see the referrer your browser is sending:

**Referrer Check**
[https://www.whatismybrowser.com/detect/what-is-my-referrer/](https://www.whatismybrowser.com/detect/what-is-my-referrer/)

You should see something like:
`https://github.com/...`
If no referrer appears, your browser or an extension may be stripping it.

---

## **2. Test the protected web app link**

Click the link below **from this README** to generate a GitHub referrer:

**Test App Link**
[https://firststep.throughlinecare.com/throughline/chat/explore-concern](https://firststep.throughlinecare.com/throughline/chat/explore-concern)
[https://staging.firststep.throughlinecare.com/firststep/chat/off-boarding-character-ai-imported-2](https://staging.firststep.throughlinecare.com/firststep/chat/off-boarding-character-ai-imported-2)
[https://firststep-studio-4w8nihsiu-throughline.vercel.app/firststep/chat/off-boarding-character-ai-imported-2](https://firststep-studio-4w8nihsiu-throughline.vercel.app/firststep/chat/off-boarding-character-ai-imported-2)

If the firewall rule is working correctly:

* Access **should be allowed** when clicked from here (referrer from `github.com`)
* Access **should be blocked** if you open the same link directly or paste it into your address bar

---

## **How this works**

GitHub sends a referrer header whenever you click an external link.
Our firewall checks this header and decides whether to allow or block access.

To verify:

* Step 1 shows your current referrer
* Step 2 confirms whether the firewall grants access when receiving a valid referrer
