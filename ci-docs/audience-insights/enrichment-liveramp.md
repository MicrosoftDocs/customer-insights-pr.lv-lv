---
title: LiveRamp identitātes datu bagātināšana
description: Bagātiniet klientu profilus ar LiveRamp datiem.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ee65cb49447df61dd5c298a84ad21bc119ead558
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373075"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Bagātināt klientu profilus ar LiveRamp identitātes datiem (Preview) 

LiveRamp nodrošina deterministisku bezsaistes identitātes izšķirtspēju un klientu datu konsolidāciju. Jūs varat kartēt personas identifikatorus savos klientu datos Uz AbiliTec identitātes grafiku un saņemt AbiliTec identifikācijas datus. Pēc tam varat izmantot šos PERSONAS, lai labāk apvienotu klientu datus. 

## <a name="prerequisites"></a>Priekšnoteikumi 

Lai konfigurētu bagātināšanu, jāievēro šādi priekšnosacījumi: 

- Jums ir aktīvs LiveRamp abonements. Lai saņemtu abonementu, sazinieties ar LiveRamp konta komandu vai lai [dynamics@liveramp.com](mailto:dynamics@liveramp.com) iegūtu papildinformāciju.   

- Aktīvs AbiliTec abonements ar klienta ID un noslēpums, lai piekļūtu API. Plašāku informāciju skatiet [AbiliTec API Developer Hub](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Atbalstītās valstis/reģioni 

Pašlaik mēs atbalstām klientu profilu bagātināšanu ar LiveRamp datiem tikai Amerikas Savienotajās Valstīs. 

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana 

1. Dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**. 

1. Elementā **Identitāte atlasiet** Bagātināt manus **datus**. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Identitātes elements bagātināšanas pārskata lapā.":::

1. Atlasiet [savienojumu](connections.md) nolaižamajā sarakstā. Ja nav pieejamu savienojumu, sazinieties ar administratoru. Ja esat administrators, varat izveidot savienojumu, atlasot **Pievienot savienojumu**. Nolaižamajā sarakstā izvēlieties **LiveRamp**. 

1. Atlasiet **Tālāk** un izvēlieties **klientu datu kopu**, kuru vēlaties bagātināt ar LiveRamp identitātes datiem. Varat atlasīt entītiju Klients *,* lai bagātinātu visus klientu profilus, vai atlasīt segmenta *entītiju, lai bagātinātu* tikai šajā segmentā iekļautos klientu profilus. 

1. Atlasiet **Tālāk** un definējiet, kāda tipa lauki no jūsu vienotajiem profiliem ir jāizmanto, lai meklētu atbilstošus identitātes datus no LiveRamp. Nepieciešams vismaz viens no laukiem **Nosaukums un adrese**, **Tālrunis** vai **E-pasts**. 

   > [!TIP]
   > Jo vairāk atslēgas identifikatoru un lauku tiek kartēti, jo lielāka ir lielāka atbilstības līmeņa iespējamība 

1. Kartējiet laukus no jūsu vienotās *klientu* entītijas, kas tiks izmantoti saskaņošanai ar LiveRamp AbiliTec ID grafiku. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="LiveRamp bagātināšanas datu kartēšanas opcijas.":::

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**. 

1. Norādiet **bagātināšanas nosaukumu** un izvades **entītiju**. 

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**. 

## <a name="configure-the-connection-for-liveramp"></a>LiveRamp savienojuma konfigurēšana 

Lai konfigurētu savienojumus, jums ir jābūt [administratoram](connections.md). Konfigurējot bagātināšanu, atlasiet Pievienot savienojumu **vai dodieties uz** AdminConnections **·** > **un atlasiet** Iestatīt **LiveRamp** elementā **.** 

:::image type="content" source="media/liveramp-connection.png" alt-text="Konfigurācijas rūts, lai iestatītu savienojumu ar liveramp AbiliTec pakalpojumu.":::

1. Parādāmajam **nosaukumam** ievadiet savienojuma nosaukumu. 

1. Norādiet derīgu LiveRamp klienta ID un noslēpumu. 

1. Pārskatiet un sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atzīmējot izvēles rūtiņu **Piekrītu**. 

1. Lai pārbaudītu konfigurāciju, atlasiet **Pārbaudīt**. 

1. Lai pabeigtu savienojumu, atlasiet **Saglabāt**. 

## <a name="enrichment-results"></a>Bagātināšanas rezultāti 

Lai sāktu bagātināšanas procesu, komandjoslā atlasiet Palaist. Varat arī ļaut sistēmai automātiski palaist bagātināšanu kā daļu [no ieslodzījuma atsvaidzināšanas](system.md#schedule-tab). Apstrādes laiks ir atkarīgs no klientu datu lieluma. 

Kad bagātināšanas process ir pabeigts, jūs varat pārskatīt jaunizveidoto klientu profilu datus sadaļās **Bagātinātā bagātināšana**. Turklāt jūs redzēsit pēdējā atjauninājuma laiku un bagātināto profilu skaitu. 

Detalizētam katra bagātinātā profila skatam varat piekļūt, atlasot **Skatīt bagātinātos** datus. 

## <a name="next-steps"></a>Nākamās darbības

Pilnveidojiet savus bagātinātos klientu datus. Izmantojiet AbiliTec PERSONAS, lai konsolidētu debitoru profilus skatā, kas balstīts uz personu. 
[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība 

Kad iespējojat Dynamics 365 Customer Insights iespēju pārsūtīt datus liveramp, jūs atļaujat pārsūtīt datus ārpus atbilstības robežas, ieskaitot potenciāli sensitīvus Dynamics 365 Customer Insights datus, piemēram, Personas datus. Korporācija Microsoft pārsūtīs šādus datus pēc jūsu norādījuma, taču jūs esat atbildīgs par to, lai LiveRamp atbilstu visām jūsu konfidencialitātes vai drošības saistībām. Lai iegūtu papildinformāciju, pārskatiet [Microsoft paziņojumu par konfidencialitāti](https://go.microsoft.com/fwlink/?linkid=396732). Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
