

## Çfarë realizova
Në këtë projekt kam realizuar faqen responsive të programit të një festivali shkencor.
- Ndërtova një menu navigimi fleksibile me **Flexbox** që përshtatet sipas ekranit dhe është tëpër e lehtë për t'u naviguar përmes tastierës (`Tab` / `Shift+Tab`).
- Krijova 6 karta aktivitetesh me **CSS Grid**, ku numri i kolonave ndryshon sipas ekranit (1, 2, ose 3 kolona).
- Asnjë element nuk përdor lartësi fikse për tekstin, imazhet janë plotësisht fleksibile (`width: 100%`, `height: auto`), dhe faqja nuk ka scroll horizontal.

---

## Hapat e hapjes
1. Klono ose shkarko këtë repository.
2. Navigo te dosja `JavaIV/`.
3. Hap skedarin `index.html` në çfarëdo shfletuesi (Browser) si Chrome, Firefox, apo Edge (ose përdor shtojcën *Live Server* në VS Code).

---

## Testimi Responsive (Rezultatet)

### Testi 1: Rezolutë 360 px (Pajisje Mobile)
* **Hyrja:** Ekran me gjerësi 360 px (p.sh. Mobile / Chrome DevTools).
* **Rezultati i pritur:** Faqja shfaq vetëm 1 kolonë kartash. Nuk ka scroll horizontal. Menuja renditet vertikalisht ose në linja fleksibile.
* **Rezultati i marrë:** Faqja shfaqi saktësisht 1 kolonë. Teksti u përshtat pa dalë jashtë kornizave. Scroll horizontal = 0. 
### Testi 2: Rezolutë 768 px (Tablet)
* **Hyrja:** Ekran me gjerësi 768 px.
* **Rezultati i pritur:** Faqja shfaq saktësisht 2 kolona kartash (rregulli 600px - 899px).
* **Rezultati i marrë:** Grid u rindërtua me 2 kolona të barabarta. Të gjitha kartat mbajnë lartësi fleksibile sipas përmbajtjes. 

### Testi 3: Rezolutë 1280 px (Desktop)
* **Hyrja:** Ekran me gjerësi 1280 px.
* **Rezultati i pritur:** Faqja shfaq 3 kolona kartash (rregulli ≥ 900px).
* **Rezultati i marrë:** Kartat u shfaqën në 3 kolona simetrike. Hapësirat (gap) dhe menuja në header u shtrinë në mënyrë elegante.

### Testi 4: Navigimi me Tastierë
* **Hyrja:** Përdorimi i tastit `Tab` për të naviguar nëpër menu dhe lidhjet e detajeve.
* **Rezultati i pritur:** Të gjitha lidhjet fokusohen me radhë, kanë tregues vizual (`outline`) dhe butoni "Skip to content" shfaqet gjatë fokusit të parë.
* **Rezultati i marrë:** Menuja dhe kartat funksionojnë 100% me tastierë.

---

## Sfida e Transferimit
U testua një karta e parë me një titull prej më shumë se 100 karakteresh:
> *"Ligjëratë Speciale mbi Zhvillimin e Inteligjencës Artificiale dhe Ndikimin e Saj në Shoqërinë Moderne të Shekullit XXI"*

**Zgjidhja:** Duke përdorur `overflow-wrap: break-word;` dhe `word-break: break-word;` së bashku me eliminimin e lartësive fikse (`height`), karta u zgjerua automatikisht në mënyrë vertikale pa prishur dizajnin e kartave të tjera në rrjet (grid) dhe pa krijuar scroll horizontal.

---

## Reflektim individual

**Kur do të zgjidhje Flexbox dhe kur Grid?**

* **Flexbox (1D - Njëdimensional):** Do ta zgjidhja kur më nevojitet të rreshtoj elemente në një drejtim të vetëm (ose vetëm në rresht, ose vetëm në kolonë). Është ideal për komponentë të vegjël ose linearë si: menu navigimi, shirita veglash (toolbars), linjëzimin e ikonave me tekst, apo shpërndarjen e hapësirës brenda vetë një karte (p.sh. shtytja e butonit apo orarit në fund të kartës me `margin-top: auto`).
* **CSS Grid (2D - Dydimensional):** Do ta zgjidhja kur duhet të ndërtoj strukturën kryesore të faqes ose kur më nevojitet të organizoj përmbajtjen njëkohësisht në rreshta dhe kolona. Është zgjidhja perfekte për rrjeta kartash (card layouts), galeri imazhesh, apo ndarjen e faqes në zona kryesore (Header, Sidebar, Main Content, Footer), pasi mundëson kontroll të plotë mbi numrin e kolonave dhe përshtatjen responsive me Media Queries.

---

## Deklarimi i AI dhe Burimev- **Asistenca nga AI:** AI u përdor për strukturimin e ideve, rregullimin e CSS-it për parandalimin e rrjedhjes së tekstit të gjatë (`overflow-wrap`), si dhe për formatimin standard të dokumentacionit në README.md.
