# ESPeasy för Onsdagsklubben
20180106

ESPeasy beskrivs här: 
https://www.letscontrolit.com/wiki/index.php/ESPEasy.

Här är en sammanfattning av de viktigaste stegen.

1. Ladda ner källkoden (http://www.letscontrolit.com/downloads/ESPEasy_R120.zip) som ska laddas ner i 8266 kortet. 
En förutgåva av ESPeasy 2.0 finns också att prova (https://github.com/letscontrolit/ESPEasy/releases). 
Packa upp filerna till valfri katalog.
2. Anslut ett 8266-kort till datorn och dubbelklicka på filen flash. 
(lista över kort som stöds https://www.letscontrolit.com/wiki/index.php/ESP_Hardware)
Svara på ett par frågor (portnummer, 4096 & 120 ) och ESPeasy laddas till kortet. (tar ca 1 min)
3. Kortet blir en Wifi accesspunkt  med namnet ”ESP…”. 
Anslut till ”ESP..” nätet med mobiltelefon/padda. Lösenordet är  ’configesp’. 
Surfa in på 192.168.4.1. 
**OBS viktigt att surfa in till adressen. Om man använder den automatiska vidarekopplingen till startmenyn så kommer man
inte att hinna se processorns nya ip adress.** 
Tillgängliga Wifi nät som kortet kan se listas. Välj nät och ange lösenord. A
vvakta medans kortet loggar in på nätet
(20sek). Kortets nya IP adress visas sen i fönstret.
4. Kortet som nu är en ESPeasy webserver presenterar ESPeasy menyer för konfigurering av systemet.
5. Nu är det bara att ansluta hårdvara koppla och konfigurera. 
Tillbehör som stöds finns här https://www.letscontrolit.com/wiki/index.php/Devices

Några viktiga saker att tänka på:

* När man under devices anger sin hårdvara tänk på att:
   * ”Enabled” ska kryssas i.
   * ”Delay” är uppdateringstintervall. Om man ska skicka till ThingSpeak måste man ta det lugnt. 30 sek funkar.
   * IDX nummer ska anges och vara unikt.
   * Send to controller ska vara kryssat om data ska skickas vidare.
   * Glöm inte att trycka på ”Submit” för att spara.
* När data ska presenteras på display på raderna ”LineX:” är formatet följande ”[Name#Value Name] text”. Om man under devices har en DS18b20
(termometer) med ”Name=TermDS18” och ”Value Namn=Temp” så kan man t ex skriva ”[TermDS18#Temp] °C”.
* Om data ska skickas till ThingSpeak så måste: 
   * ”Tools-Advanced-Message Delay” sättas till minst 15000 mS. 
   * Under ”Controllers-Controllers Settings”
      * ”Protocol”=”ThingSpeak”
      * ”Locate Controller”=”Use Hostname”
      * ”Controller Hostname”=” api.thingspeak.com”
      * “Controller Password”= [Här anges den nyckel man får när man skapar en ”Channel” på ThingSpeak]
* Under ”Tools” finns en funktion ”I2C Scan” som är bra att köra när man kopplat klart”. Den presenterar anslutna I2C enheter.

## Enkel labb

Detta prov kräver ingen ansluten hårdvara till 8266. Förutsättning är att man har laddat ESPeasy till en 8266 och anslutit den till sitt Wifi.

1. Under ”Devices” “Task”=1 (Edit) Välj ”Device”=” System Info”. Välj sen ”Name” =”uptime”, Delay”=”60”, “IDX”=1, “Indicator”=”Uptime”
och “Value Name 1” =”uptime. Spara med “Submit”.
2. Under ”Devices” “Task”=2 (Edit) Välj ”Device”=” System Info”. Välj sen ”Name” =”rssi”, Delay”=”60”, “IDX”=2, “Indicator”=”Wifi
RSSI” och “Value Name 1” =”rssi. Spara med “Submit”.
3. Under ”ToolsàAdvanced” sätt ”Message Delay (ms)”till  15000. Spara med “Submit”.
4. Under ”Config” gör följande val: ”Protocol”=”ThingSpeak”,
”Locate Controller”=”Use Hostname”, ”Controller Hostname”=” api.thingspeak.com”. Spara
data med ”Submit”.
5. Loggain/Skapa konto hos ThingSpeak. Följ instruktioner för att skapa en ”Channel”. 
Under ”Channel Settings” se till att ”Field” 1 och 2 är markerade.
När allt är klart kopiera nyckeln ”Write API Key” under ”Channelsà API Keys”.
6. Gå tillbaks till ESPeasy. Kopiera in nyckeln under ”ConfigàController Password:” Raden under ”Sensor Delay” anger hur ofta data skickas till ThingSpeak”. Sätt ej
snabbare än 15 sek. För denna test är 60 sek lagom. Spara med ”Submit”.
7. Om allt nu fungerar så ska data fyllas på i field 1 och 2 på Thingspeak en gång varje minut. Aktuella mätdata kan också ses till höger under ”Values” i menyn ”Devices”.  OBS att denna sida måste uppdateras manuellt.













