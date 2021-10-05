---
title: Pārvaldīt sīkfailus un lietotāja piekrišanu glabāt lietotāja datus programmā Dynamics 365 Customer Insights
description: Informācija par to, kā tiek izmantoti sīkfaili un lietotāja piekrišana, lai noteiktu tīmekļa vietnes apmeklētājus.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c824e50b723fe7f3b421048bb6ab96b7a9efc31f
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558880"
---
# <a name="manage-cookies-and-user-consent"></a>Sīkfailu un lietotāju piekrišanas pārvaldība

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights iesaistes ieskatu iespēja izmanto sīkfailus un (`localStorage`) taustiņus, lai identificētu tīmekļa vietnes lietotājus.

Sīkfaili ir mazi faili, kas glabā informācijas bitus par lietotāja mijiedarbību ar šo vietni. Tie tiek glabāti tīmekļa pārlūkprogrammās. Kad lietotāji apmeklē vietni, kurā jūsu lietotāji ir saglabājuši sīkfailus, pārlūkprogramma šo informāciju nosūta serverim, kas atgriež lietotājam unikālu informāciju. Šī ir tehnoloģija, kas ļauj, piemēram, tiešsaistes tirdzniecības grozam tajā saglabāt atlasītos elementus pat tad, ja lietotājs aiziet prom no vietnes.

## <a name="user-consent"></a>Lietotāja piekrišana

[Vispārējā datu aizsardzības regula (VDAR)](/dynamics365/get-started/gdpr/) ir Eiropas Savienības (ES) regula, kas nosaka, kā organizācijām jāapstrādā lietotāju privātums un drošība. Sīkfaili bieži glabā vai apkopo "personiskos datus", piemēram, tiešsaistes identifikatoru, uz ko attiecas VDAR. Ja jūsu uzņēmums nodarbina un/vai pārdod ES datu subjektiem, VDAR jūs ietekmē. [Uzziniet vairāk par to, kā Microsoft var palīdzēt jums izpildīt VDAR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Lai iesaistes ieskatu SDK atļautu glabāt sīkfailus vai citu sensitīvu informāciju, ir jānorāda, vai jūsu lietotāji ir piekrituši. Tā notiek, inicializējot SDK, iestatot `userConsent` konfigurācijas lauku.

Ja norādāt, ka nav lietotāja piekrišanas, SDK nesaglabās datus un nesūtīs notikumus, kurus var izmantot, lai izsekotu lietotāja rīcību. Visi iepriekš saglabātie dati tiks dzēsti no pārlūkprogrammas.

Ja nav norādīta lietotāja piekrišanas vērtība, SDK pieņem, ka lietotājs ir piekritis. Tas nozīmē, ja jūs (kā mūsu klients) nenorādāt vērtību lietotāja piekrišanai SDK, dati tiks ievākti. Tomēr, ja norādāt, ka lietotāja piekrišanas vērtībai ir jābūt "patiesai", dati netiks vākti, ja lietotājs noraida vai nesniedz skaidru piekrišanu.

Tālāk ir parādīts koda fragments, lai inicializētu tīmekļa SDK ar lietotāja piekrišanu.
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Apmeklētāju datu krātuve, izmantojot iesaistes ieskatu iespēju

### <a name="cookies"></a>Sīkfaili

- _msei
    - Glabā anonīmo lietotāja ID. Šis sīkfails ir iestatīts klientu domēnā, un tā derīgums beidzas pēc 365 dienām.

### <a name="local-storage"></a>Lokālā krātuve

Iesaistes ieskatu iespēja arī izmanto ( `localStorage`) taustiņus, lai izsekotu nejutīgus datus. Šie dati tiek pilnībā saglabāti pašā pārlūkprogrammā bez datplūsmas, kas tiek nosūtītas uz jūsu serveriem vai no tā.

- *EISession.Id*
    - Glabā informāciju par notiekošo lietotāja sesiju, piemēram, sesijas ID, kad tā sākta un kad beidzas tās termiņš.
- *EISession.Previous*
    - Saglabā iepriekš apmeklētās lapas URL pašreizējā sesijā.

Lokālās krātuves atslēgas nebeidzas automātiski, un tās tiks atiestatītas nākamās SDK sesijas laikā.

## <a name="deleting-cookies"></a>Sīkfailu dzēšana

Izmantojot pārlūkprogrammu iestatījumus, klienti jebkurā brīdī var manuāli dzēst sīkfailus un lokālās krātuves atslēgas.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
