# Mūsų namai – peržiūrėta kopija

Bazė: blakeblackshear/frigate-hass-addons b8349d6 (Frigate 0.18.2, atvaizdas ghcr.io/blakeblackshear/frigate:0.18.2). Peržiūra 2026-11-08.

Paliktas tik `frigate` (ne Full Access); kiti priedai pašalinti, kad netyčia nebūtų įdiegti.
Mūsų pakeitimai `frigate/config.yaml` (turi likti po kiekvieno atnaujinimo):
- `panel_admin: true` – Frigate skydelis tik administratoriui (originale – visiems, su pilnu valdymu);
- išimta `homeassistant_api`, `hassio_api` (priedui HA valdyti nereikia);
- išimta `homeassistant_config:rw`, `ssl` (konfigūracija – /addon_configs/…_frigate/config.yml);
- išimta `privileged: PERFMON` (tik GPU % statistika);
- įrenginiai – tik Intel GPU (`/dev/dri/renderD128`, `card0`), `usb: false`;
- išimta `go2rtc_allow_arbitrary_exec` (komandų vykdymas per kameros nustatymus).
Versija užfiksuota (`version`), nauja – tik po peržiūros.

Diegimas: Priedų parduotuvė → ⋮ → Saugyklos → `https://github.com/zygimantaspetrausk-ai/frigate-hass-addons` (tiksliai taip, be `.git` ir `/` gale).
Priedo adresas – `508911d5-frigate` (ne `ccab4aaf`): konfigūracija `/addon_configs/508911d5_frigate/config.yml`, integracijos URL `http://508911d5-frigate:5000`.
Be `hassio_api` WebRTC gali negauti vidinio adreso – jei gyvas vaizdas neveikia: `go2rtc: webrtc: candidates: [<serverio IP>:8555, stun:8555]`.
