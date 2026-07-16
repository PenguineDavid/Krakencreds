# Krakencreds
A new way to potentially end most phishing of credentials

Krakencreds are a new method in cybersecurity that aims to make the phishing of credentials implausible for most attackers. It was invented in view of how widespread the following type of attack was:
1) The attacker creates a fake site or account to impersonate a real site, trusted individual or organization.
2) Through social engineering, link spoofing or other methods, they direct users to the fake site or account.
3) The user is asked to enter their credentials (for an alleged verification, for emergency protection or simply for logging in after supposedly having been logged out), and as the page looks legitimate, they duly provide them.
4) The attacker can now enter the credentials to log into the user's account, and will often immediately change the password to permanently lock them out. If it was a site, then the credentials will either be stored for use or tested on the real site by a bot to ensure they are not incorrect. And even if the site uses 2-factor authentication (2FA), where a verification code which must be entered to log in is sent only to the user's email (and this is still the most robust method of authentication in many sites and applications at the moment), this can also be easily bypassed by mimicking the page for entering the code as well, as, if the credentials entered were indeed correct, the aforementioned bot will have triggered the code to be sent, raising no further suspicion that the login is fake. And once the user enters the code in the fake site as well, it is game over.

## The procedure
1) A new API is added to the authentication system which generates a set of Krakencreds on request (for example, a username and password). These will be completely dynamic and private to the user (if they were published on a public "[some site] Krakencreds" page, the attacker could easily handle them in the bot's code to avoid entering them). They can also be random, which is easier to implement and will trick any bot, or purposefully human-like (taken from a database of common credentials or generated from existing words, for example), which will also reliably trick humans if executed correctly.
2) A user who has noticed they are being the victim of a phishing attempt generates a set of Krakencreds and gives them to the attacker or enters them on the fake site instead of the real ones.
3) The attacker or bot enters the Krakencreds on the official site with the intent of taking control of the user's account or generating the 2FA code.
4) Upon detecting that a set of Krakencreds has been entered, the authentication system immediately triggers a double ban:
   - IP ban: all login attempts from the attacker's current IP are permanently blocked, preventing the attacker from running the phishing scheme on other devices in their location. As moving away will hardly be an option, this will be completely prohibitive.
   - 
