<h1>HTML Injection i DVWA</h1>


<h2>Allvarlighetsgrad</h2>

Medel. 6,3 enligt CVSS V3.1


<h2>Beskrivning</h2>

<b>Summering</b> <br>

Det är möjligt att injicera HTML-kod i /dvwa/vulnerabilities/xss_s/ som dirigerar om besökaren till valfri hemsida. I exemplet används google.com

<b>Steg för att återskapa</b>
1. Besök IP-adressen för Metasploitable2, i detta fall 192.168.50.133
2. Gå till DVWA
3. Logga in med U: admin P: password
4. Gå till DVWA Security i menyn till vänster (/dvwa/security.php)
5. Ändra från high till low och tryck på Submit
6. Gå sedan till XXS stored i menyn till vänster (/dvwa/vulnerabilities/xss_s/)
7. Skriv valfritt ord i fältet Name
8. Högerklicka i fältet Message och välj Inspect
9. Ändra maxlength=”50” till maxlength=”70”
10. Skriv följande i fältet Message: `<meta http-equiv="refresh" content="0;url='https://google.com'" />`
11. Tryck på Sign Guestbook
12. Sidan kommer nu att omdirigera till google.com varje gång någon går till /dvwa/vulnerabilities/xss_s/


<h2>Påverkan</h2>
En hotaktör kan lätt peka om sidan till sin egna klon för att till exempel komma över inloggningsuppgifter eller andra personuppgifter.


<h2>Motverkan</h2>
Genom att aktivt sanera inmatningen från specialtecken och till exempel genom att URL koda alla tecken så får man effektivt bort möjligheten till HTML injicering samt XSS.

<h2>I bilder</h2>

<img src="https://imgur.com/s4Wz5Y8.png" height="80%" width="80%" alt="HTML Injection Steg"/>
<br>
<img src="https://imgur.com/kUAeGUh.png" height="80%" width="80%" alt="HTML Injection Steg"/>
<br>
<img src="https://imgur.com/PmYndLV.png" height="80%" width="80%" alt="HTML Injection Steg"/>
<br>
<img src="https://imgur.com/wlVHlmp.png" height="80%" width="80%" alt="HTML Injection Steg"/>
<br>
<img src="https://imgur.com/Bxp4evz.png" height="80%" width="80%" alt="HTML Injection Steg"/>
<br>
<img src="https://imgur.com/FcgDZPg.png" height="80%" width="80%" alt="HTML Injection Steg"/>

