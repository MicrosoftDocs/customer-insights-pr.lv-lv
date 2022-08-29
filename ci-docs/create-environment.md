---
title: Jaunas vides izveide
description: Soļi, lai radītu vidi Dynamics 365 Customer Insights.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304253"
---
# <a name="create-a-new-environment"></a>Jaunas vides izveide

Pēc [abonēšanas licences iegādes Dynamics 365 Customer Insights](paid-license.md) nomnieka globālais administrators Microsoft 365 saņem e-pasta ziņojumu, kurā viņi tiek aicināti izveidot vidi. Lai sāktu, dodieties uz [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start). Šādā gadījumā sāciet ar [1. darbību: Sniedziet pamatinformāciju](#step-1-provide-basic-information).

Kad ir izveidota pirmā vide, nomnieka globālais administrators Microsoft 365 var [pievienot lietotājus no savas organizācijas kā administratorus](permissions.md). Pēc tam šie administratori var pārvaldīt lietotājus un vides. Ja jūsu organizācija iegādājas vairāk nekā vienu Customer Insights licenci, [sazinieties ar mūsu atbalsta komandu](https://go.microsoft.com/fwlink/?linkid=2079641), lai palielinātu pieejamo vides skaitu. Lai iegūtu papildinformāciju par noslodzi un pievienojumprogrammu noslodzi, pārskatiet [Dynamics 365 licencēšanas rokasgrāmatu](https://go.microsoft.com/fwlink/?LinkId=866544). Kad esat ieguvis iespēju izveidot papildu vides, dodieties uz [Sadaļu Sākt vides izveides procesu](#start-the-environment-creation-process).

> [!TIP]
> Ja vēlaties izmēģināt pakalpojumu, skatiet sadaļu [Izmēģinājumversijas iestatīšana](trial-signup.md).

## <a name="prerequisites"></a>Priekšnoteikumi

[Administratora atļaujas](permissions.md) programmā Customer Insights

## <a name="start-the-environment-creation-process"></a>Sāciet vides veidošanas procesu

1. Atveriet vides atlasītāju un atlasiet **+ Jauns**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Vides atlasītāja atlase.":::

1. Izpildiet turpmākajās sadaļās aprakstītos norādījumus, lai sniegtu visu nepieciešamo informāciju jaunai videi.

## <a name="step-1-provide-basic-information"></a>1. darbība: sniedziet pamatinformāciju

1. Izvēlieties, vai vēlaties izveidot vidi no nulles vai kopēt datus no citas vides. [Lai kopētu datus no citas vides,](#copy-the-environment-configuration) ir jāveic papildu darbības.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialoglodziņš jauna savienojuma izveidei ar Customer Insights.":::

1. Sniedziet šādu informāciju:

   - **Nosaukums**: Šīs vides nosaukums. Šis lauks jau ir aizpildīts, ja esat kopējis no esošas vides, bet varat to mainīt.
   - **Izvēlieties savu uzņēmumu**: galvenā jaunā vides mērķauditorija: individuālie patērētāji (no B-līdz C) vai [uzņēmuma konti](work-with-business-accounts.md) (no B līdz B). Ja jūsu organizācija galvenokārt veic darījumus ar privātpersonām, piemēram, mazumtirgotāju vai kafejnīcu, izvēlieties individuālus patērētājus. Ja jūsu galvenā mērķauditorija ir citi uzņēmumi, piemēram, automašīnu ražotājs vai papīra ražošanas uzņēmums, izvēlieties uzņēmuma kontus.
   - **Veids**: Vides veids: ražošana vai smilšu kaste. Smilškastes vidēs nevar veikt plānotu datu atsvaidzināšanu, un tās ir paredzētas iepriekšējai ieviešanai un testēšanai. Smilškastes vides izmanto to pašu primāro mērķauditoriju, kas ir pašlaik atlasītā ražošanas vide.
   - **Reģions**: reģions, kurā pakalpojums tiek izvietots un mitināts. Lai [izmantotu savu Azure Data Lake Storage kontu](own-data-lake-storage.md) vai [izveidotu savienojumu ar esošu Microsoft Dataverse organizāciju](customer-insights-dataverse.md), Customer Insights videi ir jāatrodas tajā pašā reģionā.

1. Atlasiet **Tālāk**.

## <a name="step-2-configure-data-storage"></a>2. darbība. Datu krātuves konfigurēšana

1. Izvēlieties, kur saglabāt Customer Insights datus:

   - **Customer Insights krātuve**: datu krātuve tiek pārvaldīta automātiski. Tā ir noklusējuma opcija, un, ja vien nav īpašu prasību par datu glabāšanu savā krātuves kontā, ieteicams izmantot šo opciju.
   - **Azure Data Lake Storage**: Jūsu konts Azure Data Lake Storage datu glabāšanai, lai jūs varētu pilnībā kontrolēt, kur dati tiek glabāti. Izpildiet sadaļā [Sava konta Azure Data Lake Storage izmantošana](own-data-lake-storage.md) norādītās darbības.

   :::image type="content" source="media/data-storage-environment.png" alt-text="Izvēlieties vēlamo opciju datu glabāšanai.":::

1. Atlasiet **Tālāk**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>3. darbība. Izveidojiet savienojumu ar Microsoft Dataverse

Ja jums ir Dataverse vide, savienojiet programmu Customer Insights. Kopīgojiet datus, lai Dataverse tos izmantotu ar biznesa lietojumprogrammām, kuru pamatā Dataverse ir, piemēram, Dynamics 365 Marketing vai modeļa vadītas lietojumprogrammas .Power Apps

1. Izpildiet darbības, kas norādītas rakstā [Darbs ar Customer Insights datiem sadaļā Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="datu koplietošana ar Microsoft Dataverse automātiski iespējotu neto jaunām vidēm.":::

1. Atlasiet **Tālāk**.

## <a name="step-4-finalize-the-settings"></a>4. darbība. Iestatījumu pabeigšana

Pārskatiet norādītos iestatījumus. Kad viss izskatās pabeigts, atlasiet opciju **Izveidot**, lai iestatītu vidi.

Lai vēlāk mainītu dažus iestatījumus, skatiet sadaļu [Vides](manage-environments.md) pārvaldība.

## <a name="work-with-your-new-environment"></a>Darbs ar jauno vidi

Lai palīdzētu sākt Customer Insights konfigurēšanu, pārskatiet šos rakstus:

- [Pievienojiet vairāk lietotāju un piešķiriet atļaujas](permissions.md).
- [Izgūstiet savus datu avotus](data-sources.md) un palaidiet tos [datu unificēšanas procesā](data-unification.md), lai iegūtu [vienotos klientu profilus](customer-profiles.md).
- [Bagātināt vienotos klientu profilus](enrichment-hub.md) vai [palaist prognozējošus modeļus](predictions-overview.md).
- [Izveidojiet segmentus](segments.md), lai grupētu klientus un [pasākumus](measures.md) KPI pārskatīšanai.
- [Iestatiet savienojumus](connections.md) un [eksportu](export-destinations.md), lai apstrādātu datu apakškopas citās lietojumprogrammās.

## <a name="copy-the-environment-configuration"></a>Izveidojiet vides konfigurācijas kopiju

Ja kā administrators izvēlējāties kopēt konfigurāciju no esošas vides, atlasiet no visu organizācijā pieejamo vides saraksta.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Vides iestatījumos redzamo iestatījumu opciju ekrānuzņēmums.":::

Tiek kopēti tālāk norādītie konfigurācijas iestatījumi.

- Datu avoti, kas importēti, izmantojot Power Query
- Datu apvienošanas konfigurācija
- Segmenti
- Mērījumi
- Attiecības
- Darbības
- Meklēšanas un filtrēšanas rādītājs
- Eksportēšanas darbības
- Atsvaidzināt grafiku
- Bagātinājumi
- Prognoze modeļi
- Lomu piešķiršana

### <a name="set-up-a-copied-environment"></a>Kopētas vides iestatīšana

Kopējot vides konfigurāciju, tiek parādīts apstiprinājuma ziņojums, kad ir izveidota kopētā vide. Veiciet tālāk norādītās darbības, lai apstiprinātu akreditācijas datus.

1. Atlasiet **Doties uz datu avotiem**, lai skatītu datu avotu sarakstu. Visos datu avotos tiek rādīts **statuss Obligāts** akreditācijas dati.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Kopēto un autentifikācijai nepieciešamo datu avotu saraksts.":::

1. Rediģējiet datu avotus un ievadiet akreditācijas datus, lai tos atsvaidzinātu. Datu avoti no mapes Common Data Model, un Dataverse tie ir jāizveido manuāli ar tādu pašu nosaukumu kā avota vidē.

1. Pēc datu avotu atsvaidzināšanas dodieties uz **Dati** > **Apvienot**. Šeit atradīsit avota vides iestatījumus. Rediģējiet tos pēc vajadzības vai atlasiet **Unify** > **Unify Unify klientu profilus un atkarības**, lai sāktu datu apvienošanas procesu un izveidotu vienotu klienta entītiju.

   > [!TIP]
   > Kontiem un kontaktpersonām atlasiet **Unify kontu** > **unificēt profilus un atkarības**.

1. Kad datu apvienošana ir pabeigta, dodieties uz **Mēri** un **segmenti, lai tos** atsvaidzinātu.

1. Dodieties uz **Administratoru** > **savienojumi**, lai atkārtoti autentificētu savienojumus jaunajā vidē.

1. Dodieties uz **sadaļu Datu** > **bagātināšana** un **datu** > **eksportēšana**, lai tos atkārtoti aktivizētu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
