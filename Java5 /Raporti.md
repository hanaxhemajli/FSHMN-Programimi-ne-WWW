# Raporti i çiftit
Emrat:Hana; 
shfletuesi/versioni:

## Matjet
Matjet
| Objekt | Dimensione ose kodekë | Bytes | Vërejtje |
|---|---|---:|---|
| scene-master.png | 800×450 | 350,000 | Master PNG pa kompresim |
| hero real, 400 CSS px/DPR1 | 400×225 | 25,000 | currentSrc: assets/scene-400.webp |
| hero real, 400 CSS px/DPR2 | 800×450 | 52,500 | currentSrc: assets/scene-800.webp |
| scene-800.jpg / scene-800-low.jpg | 800×450 | 65,000 / 12,000 | artefaktet: me cilësi 8 ka bllokim dhe humbje detajesh |
| demo.mp4 | container: MP4 ; video: H.264 ; audio: AAC | 450,000 | Luhet mirë |
| demo.webm | container: WebM ; video: VP9 ; audio: Opus | 380,000 | Luhet mirë |

## Llogaritjet
1. 800×450 RGB, 24 bit/piksel, pa kompresim/metadata:1,080,000 bytes. Sa për RGBA 32-bit? 1,440,000 bytes.bytes.
2. Kursimi ndaj master-it: (bytes_master − bytes_hero) / bytes_master × 100 = 85%
3. 400 CSS px në DPR=2 kërkon afërsisht 800 pikselë burimi në gjerësi.
4. Video me bitrate total 800 kbit/s për 5 s: afërsisht 500,000 bytes para overhead. Kjo është hipotetike, jo bitrate i matur i skedarit demo.
Llogaritjet
1. 800×450 RGB, 24 bit/piksel, pa kompresim/metadata: 1,080,000 bytes. Sa për RGBA 32-bit? 1,440,000 bytes.
2. Kursimi ndaj master-it: (350,000 − 52,500) / 350,000 × 100 = 85%
3. 400 CSS px në DPR=2 kërkon afërsisht 800 pikselë burimi në gjerësi.
4. Video me bitrate total 800 kbit/s për 5 s: afërsisht 500,000 bytes para overhead. Kjo është hipotetike, jo bitrate i matur i skedarit demo.

## Arsyetimi (maksimumi 200 fjalë gjithsej)
- Pse SVG për logo dhe WebP/JPEG për hero? Çfarë humbet gjatë kompresimit dhe çfarë nuk rikthen interpolimi?
SVG vs WebP/JPEG:** SVG shkallëzohet pafundësisht pa humbje cilësie (ideal për logo). WebP/JPEG ofrojnë kompresim efikas për foto. Interpolimi krijon pikselë artificialë, por nuk kthen detajet e humbura.

SVG përdoret për logon pasi shkallëzohet pa humbje cilësie; WebP/JPEG për hero ofrojnë kompresim më të mirë. Interpolimi shton pikselë të përafruar por nuk kthen detajet e humbura
- Pse PNG alpha ka sjellje tjetër nga GIF mbi sfond të errët?
PNG alpha ruan transparencën graduale në skaje pa lënë halo të bardhë, ndërsa GIF ka vetëm transparencë binare (1-bit).
-Alpha PNG vs GIF: PNG alpha ka transparencë graduale (8-bit alpha), kurse GIF ka vetëm 1-bit alpha që lë halo të bardhë. Alpha në sfond nuk ndikon te opaciteti i tekstit, ndryshe nga `opacity` i prindit.
 Dalloni opacity të prindit nga alpha e sfondit.
- RGB/CMYK/HSL: cili përdoret për ekran, cili për shtyp dhe pse ndryshon pamja? Dalloni lightness nga kontrasti.
- RGB / CMYK / HSL:*RGB përdor model aditiv për ekrane; CMYK përdor subtraktiv për shtyp (boja thith dritën). Lightness mat ndriçimin e ngjyrës, ndërsa kontrasti mat diferencën midis dy ngjyrave.
RGB përdoret për ekranet (shtohet drita), CMYK për shtyp (zhytet boja). Lightness ndryshon shkëlqimin e ngjyrës, ndërsa kontrasti mat diferencën ndërmjet dy ngjyrave fqinje.
- Pse paleta me dithering nuk ka më shumë ngjyra reale? A janë RLE dhe LZW i njëjti algoritëm? A është TIFF domosdoshmërisht lossless? Jepni një përdorim të favicon dhe një rol të mundshëm AVIF.
- Paleta, Dithering & Formate: Dithering simulon ngjyra duke shpërndarë pikselë me ngjyra ekzistuese. RLE dhe LZW janë algoritme të ndryshme. TIFF mund të jetë edhe lossy edhe lossless. Favicon identifikon faqen në tab, ndërsa AVIF ofron kompresim shumë të lartë modern.
Dithering shpërndan gabimin e kuantizimit për të simuluar ngjyra shtesë. RLE dhe LZW janë algoritme të ndryshme kompresimi. TIFF mund të jetë edhe lossy edhe lossless. Favicon shërben për identifikimin e skedait në tab, ndërsa AVIF ofron efikasitet shumë të lartë kompresimi.
- Codec vs Container:Codec është algoritmi i ngjeshjes (p.sh. H.264), ndërsa Container është mbështjellësi (p.sh. MP4). Manifesti tregon kodekun real; prapashtesa e skedarit mund të jetë e rreme.
- Dalloni codec nga container dhe lossless nga lossy. Çfarë informacioni jep manifesti që prapashtesa nuk e garanton?
Codec-u është algoritmi i kodimit/dekodimit, ndërsa container-i është paketimi i skedarit. Manifesti jep të dhëna të sakta teknike që prapashtesa nuk i garanton.

## Provat reale
- [ ] Pa 404 për burimet aktive.
- [ ] Hero: currentSrc, madhësia CSS dhe DPR të shënuara.
- [ ] Logo PNG/SVG, badge në dy sfonde, dy JPEG dhe dithering të krahasuara.
- [ ] Video WebM/MP4 dhe audio Ogg/MP3 provuar veçmas.
- [ ] Captions shqip dhe alternativat tekstuale.
- [ ] Kontrasti --text/--surface: 12.5:1 (mjeti/metoda:DevTools Accessibility).
- [ ] Tab, ekran 375px, zoom 200%.
Çifti rishikues dhe një vërejtje:Yllka Dedinaca .Vërejtje: Kontrolloni që teksti në status të ketë kontrast të mjaftueshëm edhe kur ndryshohet madhësia e dritares në mobile.
Test i pakryer ose format i pambështetur: Test i pakryer ose format i pambështetur: Asnjë problem madhor; të gjitha formatet (WebM, MP4, Ogg, MP3) u luajtën saktë në Chrome. Skedarët e vjetër që mungonin (si poster-missing.jpg) u zëvendësuan me sukses.
AI dhe verifikimi i sugjerimit: U përdor sugjerimi nga AI për strukturën e tag-ut <picture> me srcset dhe sizes për imazhin hero. E verifikova në Network dhe konsolë duke lexuar vlerën e saktë të currentSrc në DPR=1 dhe DPR=2.

