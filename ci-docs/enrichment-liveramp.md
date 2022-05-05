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
ms.openlocfilehash: 0727818f6df565d9a031966a68d521ae7167e484
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643187"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Bagātiniet klientu profilus ar LiveRamp identitātes datiem (Preview) 

LiveRamp nodrošina deterministisku bezsaistes identitātes izšķirtspēju un klientu datu konsolidāciju. Klienta datu personiskos identifikatorus varat kartēt uz AbiliTec identitātes grafiku un saņemt AbiliTec ID. Pēc tam varat izmantot šos ID, lai labāk apvienotu klientu datus. 

## <a name="prerequisites"></a>Priekšnoteikumi 

Lai konfigurētu bagātināšanu, jāievēro šādi priekšnosacījumi: 

- Jums ir aktīvs LiveRamp abonements. Lai iegūtu abonementu, sazinieties ar LiveRamp konta komandu vai lai iegūtu papildinformāciju [dynamics@liveramp.com](mailto:dynamics@liveramp.com).   

- Aktīvs AbiliTec abonements ar klienta ID un noslēpumu, lai piekļūtu API. Papildinformāciju skatiet abiliTec [API izstrādātāju centrmezglā](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Atbalstītās valstis/reģioni 

Pašlaik mēs atbalstām klientu profilu bagātināšanu tikai ar LiveRamp datiem Amerikas Savienotajās Valstīs. 

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana 

1. Dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**. 

1. Elementā Identitāte **atlasiet** Bagātināt manus **datus**. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Identitātes elements bagātināšanas pārskata lapā.":::

1. Atlasiet [savienojumu](connections.md) nolaižamajā sarakstā. Ja nav pieejamu savienojumu, sazinieties ar administratoru. Ja esat administrators, varat izveidot savienojumu, atlasot **Pievienot savienojumu**. Nolaižamajā sarakstā izvēlieties **LiveRamp**. 

1. Atlasiet **Tālāk** un izvēlieties **klienta datu kopu**, kuru vēlaties bagātināt ar LiveRamp identitātes datiem. Varat atlasīt entītiju Klients *,* lai bagātinātu visus klientu profilus, vai atlasīt segmenta *entītiju*, lai bagātinātu tikai šajā segmentā esošos klientu profilus. 

1. Atlasiet **Tālāk** un definējiet, kāda tipa lauki no jūsu vienotajiem profiliem jāizmanto, lai meklētu atbilstošus identitātes datus no LiveRamp. Nepieciešams vismaz viens no laukiem **Nosaukums un adrese**, **Tālrunis** vai **E-pasts**. 

   > [!TIP]
   > Jo vairāk atslēgu identifikatoru un lauku kartējat, jo lielāka iespēja, ka būs lielāks atbilstības līmenis 

1. Kartējiet vienotās *klienta entītijas laukus*, kas tiks izmantoti saskaņošanai ar LiveRamp AbiliTec ID grafiku. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="LiveRamp bagātināšanas datu kartēšanas opcijas.":::

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**. 

1. Norādiet **bagātināšanas un entītijas** Izvades **nosaukumu**. 

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**. 

## <a name="configure-the-connection-for-liveramp"></a>LiveRamp savienojuma konfigurēšana 

Lai konfigurētu savienojumus, [jums jābūt administratoram](connections.md). Konfigurējot bagātināšanu, atlasiet **Pievienot savienojumu** vai dodieties uz **AdminConnections** > **un** atlasiet **Iestatīt** uz **LiveRamp** elementa. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Konfigurācijas rūts, lai iestatītu savienojumu ar LiveRamp AbiliTec pakalpojumu.":::

1. Parādāmajam **vārdam** ievadiet savienojuma nosaukumu. 

1. Norādiet derīgu LiveRamp klienta ID un noslēpumu. 

1. Pārskatiet un sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atzīmējot izvēles rūtiņu **Piekrītu**. 

1. Lai pārbaudītu konfigurāciju, atlasiet **Pārbaudīt**. 

1. Lai pabeigtu savienojumu, atlasiet **Saglabāt**. 

## <a name="enrichment-results"></a>Bagātināšanas rezultāti 

Lai sāktu bagātināšanas procesu, komandjoslā atlasiet Palaist. Varat arī ļaut sistēmai automātiski palaist bagātināšanu kā daļu no plānotas [atsvaidzināšanas](system.md#schedule-tab). Apstrādes laiks ir atkarīgs no klientu datu lieluma. 

Kad bagātināšanas process ir pabeigts, varat pārskatīt nesen bagātināto klientu profilu datus sadaļāMy **bagātinājumi**. Turklāt jūs redzēsit pēdējā atjauninājuma laiku un bagātināto profilu skaitu. 

Detalizētu katra bagātinātā profila skatu var piekļūt, atlasotSkatīt **bagātinātos** datus. 

## <a name="next-steps"></a>Nākamās darbības

Pilnveidojiet savus bagātinātos klientu datus. Izmantojiet AbiliTec ID, lai konsolidētu klientu profilus personas skatā. 
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība 

Kad iespējojat Dynamics 365 Customer Insights pārsūtīt datus uz LiveRamp, jūs atļaujat pārsūtīt datus ārpus atbilstības robežas, tostarp potenciāli sensitīvus Dynamics 365 Customer Insights datus, piemēram, Personas datus. Microsoft pārsūtīs šādus datus pēc jūsu norādījumiem, bet jūs esat atbildīgs par to, lai LiveRamp atbilstu visiem jūsu konfidencialitātes vai drošības pienākumiem. Lai iegūtu papildinformāciju, pārskatiet Microsoft paziņojumu par [konfidencialitāti](https://go.microsoft.com/fwlink/?linkid=396732). Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti. 


[!INCLUDE [footer-include](includes/footer-banner.md)]
