# Gecontroleerde proefcollectie: 102 pagina’s, 26 edities

De collectie is uitgebreid en alle 102 pagina’s hebben de werkende detectie/OCR-pipeline, paginabrede herstelcontrole, rolcontrole en automatische eindcontrole doorlopen. De bevroren eindvariant is **corrected_final_v3**, versie **0.3.2-source-boundary-reviewed**. De brongecontroleerde fouten zijn hersteld en opnieuw gecontroleerd. Dit is een controleerbare onderzoeks- en reviewcollectie; volledige automatische artikelreconstructie is **niet opgelost**.

De vervolgproeven leverden ook na verbeterde prompts, expliciete kopcontext, echte native thinking en een binaire bron-doelproef aantoonbaar verkeerde antwoorden. Daarom zijn geen automatische verbindingen of automatische eindbeslissingen geaccepteerd. Alle **1.272 geschikte tekstbronnen** hebben expliciet een onbesliste automatische relatiestatus. Die inventarisatie is geen uitgevoerde modelrun op 1.272 bronnen. Afzonderlijk staan **14 brongecontroleerde lokale aansluitingen, 6 waargenomen lokale eindes en 1 specifieke afwijzing** als AI-broncorrecties (*silver*). Ze vormen geen menselijke goldstandaard en bewijzen geen complete artikelen.

## Selectie en editiecontext

De oorspronkelijke 22 pagina’s uit tien edities bleven behouden. Eerst zijn alle lokaal aanwezige pagina’s van die edities toegevoegd: 40 pagina’s. Vervolgens zijn met seed **20260906**, gesorteerde editie-ID’s en een uniforme shuffle zonder teruglegging zestien overige volledige lokale edities getrokken: nog 62 pagina’s. Het resultaat is 102 pagina’s uit 26 edities; twee pagina’s overschot voorkomt het afbreken van een editie. De populatie bevatte 30.613 scans en 7.684 edities.

25 gekozen edities hebben vier scans; Het_Vaderland_19041029 heeft lokaal twee scans. Alle aangetroffen pagina’s zijn opgenomen. Geen geselecteerde bronhash komt dubbel voor; geen intern ontbrekend paginanummer is aangetroffen. Historisch ontbrekende bladen of supplementen kunnen daarmee niet worden uitgesloten. Drie titels hebben geen aangetroffen downloadmanifest. Geen gereserveerde testeditie werd getrokken. De bestaande tien edities zijn een doelgericht behouden startset; de hele collectie is dus geen zuiver willekeurige pagina-steekproef.

Manifest, populatie, seed, trekking, bronhashes en herkomst staan in de selectiebestanden. De oorspronkelijke 22 pagina’s zijn opnieuw verwerkt met de bevroren scripts; oorspronkelijke NPS/OCR-caches zijn niet blind hergebruikt. Vier aanvullende bestaande VLM-voorstellen zijn alleen na bron-/afhankelijkheidscontrole hergebruikt. Broncollectie en oorspronkelijke pipeline zijn ongemoeid gelaten.

## Werkelijk uitgevoerde modules

| Module | Afgerond | Uitkomst en beperking |
|---|---:|---|
| American Stories-detectie en Tesseract-crop-OCR | 102/102 | Geen mislukte pagina vervangen |
| Paginabrede Tesseract-OCR | 102/102 | Controle onafhankelijk van detectorboxen; dezelfde OCR-familie, geen gold |
| Paginabrede VLM-voorstellen | 102/102 | Advertenties/mastheads en aanvullende eenheden; voorstellen vereisten controle |
| Tweede tekstuele rolcontrole | 102/102; 638 eenheden | Zelfde Qwen-model; geen statistisch onafhankelijke beoordeling. Eén ontbrekende ID gericht hersteld; oorspronkelijke failure bewaard |
| Gecorrigeerde OCR, fysieke eenheden en leesvolgorde | 102/102 | Kolommen en gedrukte banden; semantische artikelidentiteit blijft voorlopig |
| Automatische eindcontrole | 102/102 | Geen schema-, crop-hash-, lege OCR- of woordbuitenboxfouten |
| Hoogrisico-grenscontrole | 31/31 passages op 23 pagina’s | Alle bronuitsnedes bekeken; negen concrete gevallen gerepareerd/hercontroleerd |
| Automatische vervolgrelaties | Onderzoek onopgelost | Begrensde proeven uitgevoerd en afgewezen; geen volledige gekozen generatierun |
| Expliciete relatiestatusinventaris | 1.272/1.272 | 93 pagina’s met tekstbronnen; negen met uitsluitend andere rollen. Deze negen zijn verwerkt, niet mislukt |

Er zijn 233.075 actieve oorspronkelijke OCR-woordrecords. Afgeleide tekstcorrecties behouden hun diplomatische OCR en eerdere AI-lezingen. Nieuwe transcriptiewoorden krijgen geen verzonnen geverifieerde woordcoördinaten. Opnieuw gesplitste stukken bewaren de eerdere grotere OCR-regio’s in de documentprovenance.

## Controle, fouten en herstel

De oorspronkelijke vooraf getrokken visuele steekproef omvat twintig volledige bronpagina’s (seed2026090602). Daarnaast zijn onder meer 137 onbekende-rolcrops op58 pagina’s, elf ontbrekende-regelgevallen, acht lege OCR-gevallen, veertien staartcontexten en bron-doelovergangen bekeken. Deze aantallen overlappen. Niet alle102 pagina’s zijn woord voor woord visueel gecertificeerd.

De volledige interne-grensscanner vond in v2 642 verdachte passages. Alle23 met meerdere kopachtige regels en alle8 met een aparte interne kop zijn afzonderlijk bronvisueel beoordeeld:31 verschillende passages op23 pagina’s.22 bleken gewone rubrieken, tabellen, dialoog, lijsten of reeds correct gescheiden inhoud. Negen vroegen herstel. De v3-scanner geeft625 signalen, waaronder reeds als gewone substructuur beoordeelde gevallen. Dat zijn geen625 bewezen fouten; de zwakkere signalen zijn niet uitputtend visueel gelabeld.

Belangrijke bewezen foutpatronen:

- **Tekstverlies ondanks geldig schema.** Detectorboxen konden tekst missen; crop-OCR kon lege of afgesneden tekst produceren terwijl de box geldig bleef. Paginabrede OCR, bronvergelijking en gerichte nieuwe crops herstellen de gevonden gevallen. De eindcontrole vindt geen volledige regel met vier ontbrekende woordcentra. Dit bewijst niet dat ieder gedrukt teken correct is herkend.
- **Meerdere berichten in één kolomvak.** Onder meer nieuws uit1928/1937 en theaterberichten uit1912 waren samengevoegd. Zichtbare koppen, scheidingsornamenten, onderwerp-/plaatswissels en bronranden onderbouwen de nieuwe fysieke bijdragen. v3 wijzigt negen pagina’s; de andere93 zijn byte-identiek aan v2.
- **Fragmenten van één eenheid los opgevoerd.** De radiotekst, het bericht over Belgen in Frankrijk en het volledige Pathé-programma waren deels over kleine OCR-supplementen verdeeld. Bronbevestigde delen zijn samengebracht. Een overlappende box vóór Allerbeste nieuws is ingekort; een ruisbox over ÉTAT CIVIL is uit de actieve tekstbronnen gehaald.
- **Advertentie-/koprollen en tekstfouten.** Meerdelige advertenties bewaren fysieke deelvakken; de omhullende rechthoek geldt niet als advertentiegrens. Gevonden rol- en transcriptiefouten zijn expliciet gecorrigeerd, waaronder Charles Meulemans, 2e ANNÉE bij Le Petit Rentier en zichtbare registercijfers. De botermarkttabel heeft een tabelrol.
- **Leesvolgorde is geen artikelvervolg.** Een model verbond een overval aan het volgende brandbericht, ondanks letterlijke citaten. Andere modellen misten duidelijke aansluitingen of sloegen een genummerd bureel over. Citaten alleen bewijzen geen berichtidentiteit. Alle ruwe antwoorden, technische fouten, afwijzingen en oude conflict-/cyclusbeslissingen blijven historisch bewaard.

Het register bevat **64 bevindingen**:63 concrete gerapporteerde defecten zijn hersteld/hercontroleerd; één resterende modelonderzoeksbevinding wordt beheerst door automatische relaties niet te gebruiken. Dat is geen semantische reparatie van het model. V3 gebruikte32 nieuwe crop-OCR-eenheden in33 uitvoeringpogingen; de eerste Pathé-tussenvariant bleef bewaard. Alle gewone woorden van iedere nieuwe recognizer-output zijn door de coördinatentransformatie behouden. Dit is een software-regressiecontrole, geen bewijs van perfecte OCR.

De zoekintegratie vindt **Charles Meulemans** terug op De_Volkswil_19120525_0004 met de juiste bronverwijzing. Ook **Société royale** vindt de gesplitste concertpassage op Gazette_de_Louvain_18950914_0003. Beide controles slagen in de daadwerkelijke v3-SQLite-index.

## Tijd en geheugen

De oorspronkelijke CPU-run duurde1.183,6 seconden met gemeten maximale RSS2,84GB; paginabrede OCR1.528,7 seconden en0,64GB. De VLM-run duurde4.778,0 seconden; de som van opgeslagen casetijden is5.002,3 seconden inclusief hergebruikte voorstellen. Ollama rapporteerde18,15GB model-VRAM; dit is geen gemeten procespiek. De volledige rolronde duurde2.128,2 seconden; een afzonderlijke retry7,8 seconden. V3’s33 gerichte OCR-pogingen tellen samen20,6 seconden recognizer-tijd; geen betrouwbare aanvullende piek-RAMmeting.

Fasen overlapten, gebruikten caches en omvatten wachttijd. Deze cijfers mogen niet tot één fictieve totale looptijd worden opgeteld. Bronvisuele beoordeling, export en alle afgewezen vervolgexperimenten staan afzonderlijk in logs; er is geen volledige end-to-endlooptijd voor succesvolle artikelreconstructie.

## Review en eindscope

De mobiele reviewqueue bevat **18 concrete brongebonden vragen**: zeven onzekere lokale aansluitingen/subsecties en elf lidmaatschapsvragen bij meerdelige advertenties. De prioriteit is een heuristiek, geen gekalibreerde foutkans. Goed/Fout bevestigt uitsluitend de getoonde aansluiting of het getoonde lidmaatschap. Volledige kolommen worden niet automatisch tot één bewezen artikel samengevoegd.

De eindpoort vereist afgeronde paginaverwerking, bekende concrete defecten gerepareerd/hercontroleerd, geldige bron-/versie-/regioverwijzingen, een bruikbare beperkte queue en volledige openlijke relatiestatus. Onopgeloste modelsemantiek wordt expliciet behouden. Verdere afleveringen buiten de gekozen edities blijven ongecontroleerd. Menselijke antwoorden kunnen later gericht herstel sturen; zij veranderen eerdere AI-oordelen niet achteraf in onafhankelijke gold.

De aparte Institutional Newspapers-proef op twintig oude pilotpagina’s hoort niet bij deze102-run of haar timing. Zij gaf geen reden de huidige detector te vervangen; haar beperkte referenties zijn evenmin onafhankelijke gold.

Bij de finale websitebeeldcontrole is de reviewcontext afzonderlijk hersteld: zes doeluitsnedes tonen nu ook twee relevante tussenkoppen en vier gedrukte sterrenscheidingen. Alle zes gewijzigde focusbeelden zijn opnieuw tegen de bron bekeken. De 18 vragen, hun onzekerheidsstatus, fysieke tekstgrenzen en alle NPS-/relatiegegevens blijven gelijk. `audit/review_context_recheck/recheck.json` bewaart voor/na-coördinaten, bronhashes en dit weergaveherstel; dit is een aparte presentatierevisie naast de 64 pipelinebevindingen.
