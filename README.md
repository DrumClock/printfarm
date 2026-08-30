# Print Farm — PWA rozcestník ke Klipper tiskárnám

Rozcestník k tiskárnám (Mainsail/Fluidd) na telefonním hotspotu.
Po nasazení na GitHub Pages z něj uděláš ikonu na ploše, která jede i offline.

## Co je v balíčku
- `index.html` — samotná aplikace
- `manifest.json` — název, ikony, celoobrazovkový režim
- `sw.js` — service worker (uloží appku do telefonu → funguje bez internetu)
- `icon-192.png`, `icon-512.png`, `icon-180.png`, `icon-maskable-512.png` — ikony

**Všechny soubory musí zůstat pohromadě v jedné složce (kořen repozitáře).**

## Nasazení na GitHub Pages
1. Vytvoř nové **public** repo (např. `print-farm`).
2. Nahraj do něj **všechny** soubory z tohoto zipu (rozbal a nahraj obsah, ne zip).
3. Repo → **Settings → Pages**.
4. Source: **Deploy from a branch**, Branch: **main**, složka **/ (root)** → **Save**.
5. Za chvíli se objeví adresa `https://TVOJE-JMENO.github.io/print-farm/`.

## Ikona na plochu
1. Tu adresu otevři v **Chrome** na telefonu.
2. **⋮ → Přidat na plochu** (u https už volba je).
3. Poprvé to nech načíst s internetem — service worker si appku uloží.
   Napříště jede i na hotspotu bez dat.

## Přidání tiskáren
V appce **+ Přidat**. Adresu zadávej jako **hostname**, ne IP —
třeba `voron24.local`, `fluiddpi.local`. Hostname se nemění, i když
hotspot přidělí jinou IP.

## Poznámky
- Když appku upravíš a nahraješ znovu, ve `sw.js` zvyš `printfarm-v1`
  na `printfarm-v2`, ať si telefon stáhne novou verzi.
- Service worker vyžaduje `https` (GitHub Pages ho má) nebo `localhost`.
  Přes `file://` je neaktivní — proto ta cesta přes GitHub Pages.
