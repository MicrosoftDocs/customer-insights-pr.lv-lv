---
title: Customer Insights izmēģinājumversijas izveide un konfigurēšana
description: Darbības, kas jāveic, lai iegūtu Dynamics 365 Customer Insights izmēģinājumversijas abonementu un to konfigurētu.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 3a235e924395a606b9332de3d205289288a597a9
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558832"
---
# <a name="set-up-a-trial-environment"></a>Izmēģinājumversijas vides iestatīšana 

Izmantojot versijas Dynamics 365 Customer Insights izmēģinājumversiju, varat pārskatīt galvenās iespējas un uzzināt vairāk par dažādiem līdzekļiem. Izmēģinājumversijas abonements tiek izdzēsts pēc termiņa beigām. Izmēģinājumversijas vides veido atsevišķi lietotāji, kas kļūst par izmēģinājumversijas administratoru. Viņi var uzaicināt citus lietotājus uz izmēģinājumversiju un konfigurēt dažādus līdzekļus.

## <a name="create-a-trial-environment"></a>Izveidojiet izmēģinājuma vidi

Izmēģinājumam varat pierakstīties [izmēģinājuma pierakstīšanās lapā](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Izvēlieties opciju **Pieteikties bezmaksas izmēģinājumam** un atlasiet **Pieteikties tūlīt**.

1. Norādiet savu darba vai mācību e-pasta adresi, pastāstiet mums vairāk par sevi un atlasiet vienumu **Darba sākšana**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialogs, lai reģistrētos izmēģinājuma instancē":::

1. Pārskatiet noteikumus un nosacījumus un tad atlasiet **Turpināt**.

1. Norādiet savas jaunās vides **nosaukumu**. 

1. Iestatiet vides **Tipu** kā **Izmēģinājumversiju**.

1. Laukā **Nozares demonstrācijas atlase** varat arī izvēlēties nozarei specifisko datu kopu. Nozares [demonstrāciju var mainīt arī](#use-industry-specific-demo-data-sets-in-audience-insights) vēlāk un sākt ar noklusējuma datu kopu.

1. Atlasiet vides **Reģionu**.

1. Ja esat Dynamics 365 organizācijas administrators: atlasiet **Papildu iestatījumus** un norādiet savas organizācijas vietrādi URL, lai izmantotu prognozes līdzekļus, piemēram, klientu trūkuma prognoze. 

1. Atlasiet **Izveidot**. 

Instalēšanas pabeigšanai ir nepieciešamas dažas minūtes. Pēc pabeigšanas tiekat novirzīts uz demonstrācijas vidi vai nozares demonstrāciju, kuru izvēlaties iepriekš minētajā darbībā. Tagad programmu varat izpētīt, izmantojot tikai lasāmus demonstrācijas datus. Lai savai videi pievienotu savus datus, skatiet rakstu [Scenārijam specifisko demonstrācijas datu izveide savā vidē](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Jaunizveidotas izmēģinājumversijas ekrānuzņēmums.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Nozarei specifisko demonstrācijas datu kopu izmantošana auditorijas ieskatos

Reālu datu avotu pievienošana ir viena no svarīgākajām darbībām, kas jāveic, izmantojot Customer Insights iespējas. Lai izmēģinātu līdzekļus, nesajaucot ar saviem datiem, varat neobligāti izmantot nozarei specifiskos demonstrācijas datus. Ir pieejamas pāris demonstrācijas datu kopas šādām nozarēm: 

-   Automobiļi
-   Banku nozare
-   Patēriņa preces
-   Valsts iestādes
-   Veselības aprūpes
-   Viesmīlība
-   Apdrošināšana
-   Ražošana
-   Profesionālie pakalpojumi
-   Mazumtirdzniecība

### <a name="see-industry-specific-demo-data-in-trials"></a>Nozarei specifisko demonstrācijas datu skati izmēģinājumversijās

Tikai lasāmai customer Insights versijai, kas pielāgota noteiktai nozarei vai scenārijam, sāciet ar demonstrācijas vidi. 
 
1.  Auditorijas ieskatos vides atlasītājā izvēlieties **Demonstrācijas** vidi.

2.  **Sākumlapas** nolaižamajā izvēlnē Atlasiet nozares demonstrāciju izvēlieties kādu no opcijām.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Izvēlieties izmēģinājumversijas vides nozari.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Scenārijam specifisko demonstrācijas datu izveide savā vidē

Kā administrators programmas galvenē atlasiet vides atlasītāju, lai izveidotu jaunu vidi. Jaunajā vidē varat konfigurēt savus datu avotus un iestatīt programmu atbilstoši savām prasībām. 

1.  Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.

2.  Lai importētu savus datu avotus, dodieties [uz rokasgrāmatu par datu uzņemšanu](data-sources.md).     
   Ja vēlaties strādāt ar datu paraugu, kas ļauj izmēģināt datu uzņemšanu, varat uzņemt nozares demonstrācijas datus savā vidē. Izvēlieties opciju **Importēt no Datahub** un veiciet tālāk norādītās darbības.

3.  Atlasiet scenārijam piemērotu nozares karti. 

4.  Pārskatiet un pēc izvēles atjauniniet ieteikto datu datu avota nosaukumu. 

5.  Atlasiet **Tālāk**, lai uzņemtu datu paraugus. 

Tagad varat izmantot uzņemtos datus, lai Customer Insights pielāgotu savam scenārijam. Lai skatītu vidi, kas raksturīga uzņemtajiem demonstrācijas datiem, izvēlieties **<Industry> Demo** opciju vides atlasītājā.

## <a name="limitations-in-trials"></a>Izmēģinājumversiju ierobežojumi

- Izmēģinājumversijas pēc noklusējuma ir aktīvas 30 dienas. Tomēr tos varat paplašināt pēc 23. dienas, kad piesakieties izmēģinājumversijai.
- Jūs nevarat izmantot savu Azure Data Lake Storage kontu, lai izvades datus glabātu izmēģinājumversijas laikā. Tomēr datus varat ievadīt no Data Lake Storage konta.
- Dataverse vidē varat glabāt līdz pat 3 GB datu, kas tiek nodrošināti automātiski, sākot Customer Insights izmēģinājumversiju.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Kopējiet datus no izmēģinājumversijas uz apmaksātu abonementu

Parasti ieteicams sākt atjaunināšanu ar saviem datiem, jauninot uz Customer Insights apmaksāto versiju. 

Ja iegādāsties pakalpojumu Customer Insights, varat arī kopēt datus no izmēģinājumversijas vides. Jums ir jābūt customer Insights izmēģinājumversijas administratoram un jūsu Microsoft 365 nomnieka globālajam administratoram vai Dynamics 365 administratoram organizācijā, lai migrētu iestatījumus no izmēģinājumversijas vides uz apmaksātu vidi. 

Pēc pieteikšanās apmaksātajā Customer Insights instancē pirmo reizi tiek piedāvāts izveidot jaunu vidi. Šajā procesā varat izvēlēties kopēt konfigurāciju no esošas vides un migrēt lielāko daļu iestatījumu. Ja jums ir iepriekšminētās atļaujas, izmēģinājumversijas vide tiks parādīta šajā sarakstā. Papildinformāciju skatiet sadaļā [Vides konfigurācijas kopēšana](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Nākamās darbības

Lai palīdzētu sākt Customer Insights konfigurēšanu, pārskatiet tālāk norādītos rakstus. 

- [Pievienojiet vairāk lietotāju un piešķiriet atļaujas](permissions.md).
- [Izgūstiet savus datu avotus](data-sources.md) un palaidiet tos [datu unificēšanas procesā](data-unification.md), lai iegūtu [vienotos klientu profilus](customer-profiles.md).
- [Bagātināt vienotos klientu profilus](enrichment-hub.md) vai [palaist prognozējošus modeļus](predictions-overview.md).
- Izveidojiet [segmentus](segments.md), lai grupētu klientus un [pasākumus](measures.md) KPI pārskatīšanai.
- Iestatiet [savienojumus](connections.md) un [eksportu](export-destinations.md), lai apstrādātu datu apakškopas citās lietojumprogrammās.
