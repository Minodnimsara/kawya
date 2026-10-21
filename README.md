# Kawya Group Management Site

A single-page website for Kawya Group (concrete yard, hardware and transport): billing and bill printing, customers, pending payments and bank cheques, stock, transport, salaries, supplies, and a password-protected finance area.

No build step and no dependencies. Everything is in `index.html`.

## Publish with GitHub Pages
1. Create a new repository on GitHub and upload all files in this folder.
2. Open **Settings > Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then Save.
4. After a minute the site is live at `https://YOUR-USERNAME.github.io/REPOSITORY-NAME/`.

## Important notes
- **Data is stored in the browser** (localStorage) of the computer in use. It is not shared between computers and is lost if browser data is cleared. Use one main computer for billing and back up regularly. A backend database is the next step for shared data.
- **Passwords are not truly secure.** The password check runs in the browser. Only a hash is stored in the code, but anyone who can read the code can try to guess it. Choose a strong password for real use, and do not rely on this for confidential data.
- **Public repository warning:** a public repository makes the code visible to everyone. Prefer a private repository if your plan supports Pages for private repos.
- **Printing:** the Print button opens the browser print dialog. Choose the Epson LQ-310 or Save as PDF. Bills are laid out for 9.5-inch continuous paper.
- **WhatsApp:** buttons open WhatsApp with the message ready to send. Fully automatic sending needs the WhatsApp Business API.

## Change the finance/fleet password
Open the browser console on any page, run the line below with your new password, and replace the value of `PH` in `index.html` with the result:

```js
crypto.subtle.digest('SHA-256', new TextEncoder().encode('NEW PASSWORD')).then(b => console.log([...new Uint8Array(b)].map(x => x.toString(16).padStart(2,'0')).join('')))
```
