---
title: Sīkfailu pārvaldība un lietotāja piekrišana lietotāju datu glabāšanai
description: Informācija par to, kā tiek izmantoti sīkfaili un lietotāja piekrišana, lai noteiktu tīmekļa vietnes apmeklētājus.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036747"
---
# <a name="manage-cookies-and-user-consent"></a>Sīkfailu un lietotāju piekrišanas pārvaldība

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights iesaistes ieskatu iespēja izmanto sīkfailus un lokālo krātuvi (`localStorage`), lai identificētu vietnes apmeklētājus.

Sīkfaili ir mazi faili, kas glabā informācijas bitus par lietotāja mijiedarbību ar šo vietni. Tie tiek glabāti tīmekļa pārlūkprogrammās. Kad lietotāji apmeklē vietni, kurā jūsu lietotāji ir saglabājuši sīkfailus, pārlūkprogramma šo informāciju nosūta serverim, kas atgriež lietotājam unikālu informāciju. Šī ir tehnoloģija, kas ļauj, piemēram, tiešsaistes tirdzniecības grozam tajā saglabāt atlasītos elementus pat tad, ja lietotājs aiziet prom no vietnes.

## <a name="user-consent"></a>Lietotāja piekrišana

[Vispārējā datu aizsardzības regula (VDAR)](/dynamics365/get-started/gdpr/) ir Eiropas Savienības (ES) regula, kas nosaka, kā organizācijām jāapstrādā lietotāju privātums un drošība. Sīkfaili bieži glabā vai apkopo "personiskos datus", piemēram, tiešsaistes identifikatoru, uz ko attiecas VDAR. Ja jūsu uzņēmums nodarbina un/vai pārdod ES datu subjektiem, VDAR jūs ietekmē. [Uzziniet vairāk par to, kā Microsoft var palīdzēt jums izpildīt VDAR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Lai iesaistes ieskatu SDK atļautu glabāt sīkfailus vai citu sensitīvu informāciju, ir jānorāda, vai jūsu lietotāji ir piekrituši. Tas notiek, inicializējot SDK.

Ja norādāt, ka nav lietotāja piekrišanas, SDK nesaglabās datus un nesūtīs notikumus, kurus var izmantot, lai izsekotu lietotāja rīcību. Visi iepriekš saglabātie dati tiks dzēsti no pārlūkprogrammas.

Ja nav norādīta lietotāja piekrišanas vērtība, SDK pieņem, ka lietotājs ir piekritis. Tas nozīmē, ja jūs (kā mūsu klients) nenorādāt vērtību lietotāja piekrišanai SDK, dati tiks ievākti. Tomēr, ja norādāt, ka lietotāja piekrišanas vērtībai ir jābūt "patiesai", dati netiks vākti, ja lietotājs noraida vai nesniedz skaidru piekrišanu.

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Apmeklētāju datu krātuve, izmantojot iesaistes ieskatu iespēju

### <a name="cookies"></a>Sīkfaili

- _msei
    - Glabā anonīmo lietotāja ID. Šis sīkfails ir iestatīts klientu domēnā, un tā derīgums beidzas pēc 365 dienām.

### <a name="local-storage"></a>Lokālā krātuve

Iesaistes ieskatu iespēja arī izmanto lokālo krātuvi (`localStorage`), lai sekotu nejutīgiem datiem. Šie dati tiek pilnībā saglabāti pašā pārlūkprogrammā bez datplūsmas, kas tiek nosūtītas uz jūsu serveriem vai no tā.

- *EISession.Id* 
    - Glabā informāciju par notiekošo lietotāja sesiju, piemēram, sesijas ID, kad tā sākta un kad beidzas tās termiņš.
- *EISession.Previous*
    - Saglabā iepriekš apmeklētās lapas URL pašreizējā sesijā.
    
Lokālās krātuves taustiņu derīgums nebeidzies automātiski. Nākamajā sesijā SDK šos iestatījumus atiestatīs.

## <a name="deleting-cookies"></a>Sīkfailu dzēšana

Izmantojot pārlūkprogrammu iestatījumus, klienti jebkurā brīdī var manuāli dzēst sīkfailus un lokālās krātuves atslēgas.


[!INCLUDE[footer-include](../includes/footer-banner.md)]