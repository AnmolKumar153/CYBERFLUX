# CyberFlux

so basically i was learning about cybersecurity and URL based attacks and i thought why not just build something instead of only reading about it. that's how this project started. it's a URL checker that looks at a link and tells you whether it seems safe or not.

it's not perfect but it covers the important stuff and it actually works, which i'm pretty happy about.

---

## what does it do

you paste a URL, click the button, and it runs 11 different checks on it right in the browser. no data goes anywhere, no server involved, everything happens locally.

the checks it runs:

- is the URL weirdly long (phishing URLs tend to be massive)
- does it use HTTPS
- is the domain actually just an IP address
- does it have sketchy words like "login", "verify", "secure", "confirm" etc.
- how many subdomains does it have
- does it have an @ symbol (this is a known trick to fool people)
- too many hyphens in the domain name
- any weird unicode characters that look like normal letters
- does the domain look like a misspelling of google, paypal, amazon etc.
- is it a URL shortener like bit.ly or tinyurl
- does the domain name look randomly generated

at the end it gives you a risk score and tells you if the URL looks safe, suspicious, or likely malicious.

---

## how to run it

it's just HTML, CSS and JS so there's nothing to install or build. the only thing is you shouldn't open the HTML file directly by double clicking it, some browsers act weird with the file:// protocol. just spin up a local server real quick, it takes like a minute.

### Windows

open command prompt or powershell and run:

```
git clone https://github.com/AnmolKumar153/CYBERFLUX.git
cd CYBERFLUX
```

if you have python (check by typing `python --version`):

```
python -m http.server 5500
```

then just go to `http://localhost:5500` in your browser and that's it.

if python isn't there, install VS Code, get the Live Server extension, open the folder and right click index.html then click "Open with Live Server". easiest option honestly.

---

### macOS

```
git clone https://github.com/AnmolKumar153/CYBERFLUX.git
cd CYBERFLUX
python3 -m http.server 5500
```

mac already has python3 so it should just work. open `http://localhost:5500` and you're good. Ctrl+C to kill the server when you're done.

---

### Linux

```
sudo apt install git        # skip if you already have it
git clone https://github.com/AnmolKumar153/CYBERFLUX.git
cd CYBERFLUX
python3 -m http.server 5500
```

same thing, go to `http://localhost:5500`. if you're on fedora or arch just swap apt for dnf or pacman.

---

### Kali Linux

git and python3 come pre-installed on kali so honestly just:

```
git clone https://github.com/AnmolKumar153/CYBERFLUX.git
cd CYBERFLUX
python3 -m http.server 5500
```

open firefox or chromium, go to `http://localhost:5500`, done.

---

## files in this project

```
CYBERFLUX/
├── index.html
├── cyberflux.css
├── about.html
├── features.html
├── contact.html
└── cyberfluxlogo.png
```

---

## stuff i know isn't perfect

the domain age check is a heuristic, not a real WHOIS lookup. doing actual WHOIS from the browser isn't possible without a backend so i made it check if the domain name looks auto-generated instead. it's not ideal but it catches some cases.

also it only reads the URL string, it doesn't actually visit the page or scan any content. so if a phishing site has a clean-looking URL it won't catch it. that's a limitation i'm aware of.

maybe someday i'll add a small backend to handle the real WHOIS stuff and a few other checks but for now this is where it's at.

---

## if you want to contribute

go ahead, open a PR or raise an issue. i'm still learning this stuff so if you see something wrong or something that could be better i genuinely want to know.

---

built by Anmol Kumar
