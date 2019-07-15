# ESPeasy för Onsdagsklubben
20190715

1.	Inledning
EspEasy är en programvara, nästan som ett  ”operativsystem”, för ESP8266. Efter att programmet installerats  sker kommunikationen med EspEasy via web-gränsyta. Det är inga ytterliggare programvaror som ska kompileras. Via EspEasy kan man mäta med anslutna sensorer och styra/mäta via IO-pinnarna på ESP8266. Via mindre textbaserade script kan man programera logiska funktioner användbart t ex för hemautomatisering. EspEasy kan också leverara data till andra Smarta hem program som Domoticz eller MQTT. Det går också bra att trigga IFTTT händelser via anrop till maker.ifttt.com. Data kan också skickas till thingspeak för grafisk presentation. Har man flera moduler med EspEasy på så kan modulerna på ett enkelt sätt kommunisera med varandra för utökad funktionallitet. Det är omöjligt att på ett enkelt sätt lista allt som EspEasy kan göra. Se vidare i användardokumentationen som finns här: https://espeasy.readthedocs.io/en/latest/.

Man behöver inte kunna programera för att använda EspEasy. All initial uppsättning görs via webgränsytor. 
En Wiki-sida med mer kompletterande info finns också: https://www.letscontrolit.com/wiki/index.php/ESPEasy#Introduction

2.	Installation av EspEasy (Instruktion för Windows)
EspEasy kan installeras på i princip alla ESP8266 baserade kretskort med serieport. Allt man behöver finns här: https://github.com/letscontrolit/ESPEasy/releases
a)	Välj att ladda ner den senaste utgåvan. Följ länken med namn ”Release mega-2019xxxx” och ladda ner zip-filen (ca 35 MB). Packa upp zipfilen i valfri katalog.
b)	Katalogen innehåller ett flertal filer men just nu är bara två stycken av intresse:
1) FlashESP8266.exe och 2) ESP_Easy_mega-2019xxxx_normal_ESP8266_4M.bin
c)	Anslut ESP modulen till valfri USB port med lämplig datakabel.
d)	Starta programmet FlashESP8266.exe. Programmet kommer att visa vilka comportar som finns att välja på. Har man bara en ESP-modul ansluten så väljer programmet automatsikt rätt port.
e)	Vid ”Firmware” välj binärfilen ESP_Easy_mega-2019xxxx_normal_ESP8266_4M.
f)	Tryck Flash för att påbörja laddningen av EspEasy. Förloppet kan följas på skärmen. Överföringen tar nästan 2 minuter.
g)	I detta läge kan man om man vill låta ett terminalprogram (t ex Putty) ansluta mot modulen på samma Comport som exe-filen använde. Inställning ska vara 115200 N 8 1.
EspEasy kommer kontinuerligt att logga data på serieporten.

3.	Aktivering
Efter installation så behöver ESP8266 modulen ansluta sig till hemmanätverket. Det görs på följande sett:
a)	Tryck reset och starta om modulen. Modulen kommer nu att agera Accesspunkt(AP) på ett Wifi- nät med namn ”ESP_Easy_0”. 
b)	Anslut till ”ESP_Easy_0” med dator, padda mobil etc. Starta en webläsare och anslut till adress 192.168.4.1.
c)	En lista visas med tillgängliga nätverk. Välj det nätverk som modulen ska arbeta på och ange även lösenord för nätverket.
d)	Modulen kommer att starta om och ansluta till nätverket som angetts. Om allt går bra kommer modulen efter 20 sekunder att ange vilken ip-adress den har fått. Notera adressen.
e)	Anslut nu dator, padda mobil etc till samma nät som modulen och ange ip-adressen som noterades ovan.
f)	Ett användargränssnitt visas och EspEasy är nu klart att användas.

4.	Användning
Fortsättning följer.











