---
title: Kā - izveidot jaunu vidi
description: Darbības, lai izveidotu vides ar Dynamics 365 Customer Insights.
ms.date: 05/31/2022
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
ms.openlocfilehash: 795eaa3598257f5188070f6ea02d04e4423b66eb
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833567"
---
# <a name="how-to-create-a-new-environment"></a>Kā: Izveidot jaunu vidi

Pēc [abonementa licences iegādes Dynamics 365 Customer Insights](paid-license.md) īrnieka globālais administrators Microsoft 365 saņem e-pasta ziņojumu, kurā viņš tiek aicināts izveidot vidi. Lai sāktu, dodieties uz [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start). Šajā scenārijā varat doties tieši uz [1. darbību: sniedziet pamatinformāciju](#step-1-provide-basic-information).

Pēc pirmās vides izveides nomnieka globālais administrators var Microsoft 365 pievienot lietotājus, [kas veido savu organizāciju kā administratorus](permissions.md). Virzoties uz priekšu, šie administratori var pārvaldīt lietotājus un vides. Ja jūsu organizācija iegādājas vairāk nekā vienu Customer Insights licenci, sazinieties ar mūsu atbalsta komandu [,](https://go.microsoft.com/fwlink/?linkid=2079641) lai palielinātu pieejamo vides skaitu. Lai iegūtu papildinformāciju par noslodzi un pievienojumprogrammu noslodzi, pārskatiet [Dynamics 365 licencēšanas rokasgrāmatu](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> Ja vēlaties izmēģināt pakalpojumu, skatiet sadaļu [Izmēģinājumversijas iestatīšana](trial-signup.md).

## <a name="prerequisites"></a>Priekšnoteikumi

Lai izveidotu vai pārvaldītu [vides, programmā Customer Insights ir nepieciešamas](permissions.md) administratora atļaujas.

## <a name="start-the-environment-creation-process"></a>Sākt vides veidošanas procesu

1. Atveriet vides atlasītāju un atlasiet **+ Jauns**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Vides atlasītāja atlase.":::

1. Sekojiet turpmākajās sadaļās izklāstītajai vadītajai pieredzei, lai sniegtu visu nepieciešamo informāciju jaunai videi. Ja iepriekš konfigurējāt vidi, varat arī [kopēt konfigurāciju](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>1. darbība: sniedziet pamatinformāciju

**Pamatinformācijas** solī izvēlieties, vai vēlaties veidot vidi, izmantojot slāpējumu, vai [kopēt datus no citas vides](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialoglodziņš jauna savienojuma izveidei ar Customer Insights.":::

Sniedziet šādu informāciju:

- **Nosaukums**: Šīs vides nosaukums. Šis lauks jau ir aizpildīts, ja esat kopējis no esošas vides, bet varat to mainīt.
- **Izvēlieties savu biznesu**: izvēlieties jaunās vides primāro auditoriju. Jūs varat strādāt ar individuāliem klientiem (B2C) vai [biznesa uzņēmumiem](work-with-business-accounts.md) (B2B). Ja jūsu organizācija galvenokārt sadarbojas ar privātpersonām, piemēram, mazumtirgotāju vai kafejnīcu, izvēlieties individuālus patērētājus. Ja jūsu galvenā auditorija ir citi uzņēmumi, piemēram, automašīnu ražotājs vai papīra uzņēmums, izvēlieties biznesa kontus.
- **Veids**: Atlasiet, vai vēlaties veidot ražošanas vai smilškastes vidi. Smilškastes vidēs nevar veikt plānotu datu atsvaidzināšanu, un tās ir paredzētas iepriekšējai ieviešanai un testēšanai. Smilškastes vides izmanto to pašu primāro mērķauditoriju, kas ir pašlaik atlasītā ražošanas vide.
- **Reģions**: Reģions, kurā tiek izvietots un viesots pakalpojums. Lai [izmantotu savu Azure Data Lake Storage kontu](own-data-lake-storage.md) vai [izveidotu savienojumu ar esošu Microsoft Dataverse organizāciju](customer-insights-dataverse.md), Customer Insights videi jābūt tajā pašā reģionā.

## <a name="step-2-configure-data-storage"></a>2. darbība. Datu krātuves konfigurēšana

**Datu glabāšanas** solī izvēlieties, kur saglabāt Customer Insights datus.

Ir divas iespējas, no kurām varat izvēlēties:

- **Customer Insights krātuve**: datu glabāšanu pārvalda Customer Insights komanda. Tā ir noklusējuma opcija, un, ja vien nav īpašu prasību par datu glabāšanu savā krātuves kontā, iesakām izmantot šo opciju.
- **Azure Data Lake Storage**: Norādiet savu Azure Data Lake Storage kontu, lai saglabātu datus, lai jums būtu pilnīga kontrole pār to, kur dati tiek glabāti. Papildinformāciju skatiet rakstā [Sava Azure Data Lake Storage konta](own-data-lake-storage.md) izmantošana.

:::image type="content" source="media/data-storage-environment.png" alt-text="Izvēlieties vēlamo opciju datu glabāšanai.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>3. darbība. Izveidojiet savienojumu ar Microsoft Dataverse

Šī **Microsoft Dataverse** darbība ļauj izveidot Customer Insights savienojumu ar savu Dataverse vidi. Koplietojiet datus ar Dataverse tiem, lai tos izmantotu biznesa lietojumprogrammās, kuru Dataverse pamatā ir, piemēram, Dynamics 365 Marketing vai modeļa vadītas lietojumprogrammas programmā Power Apps.

Atstājiet šo lauku tukšu, ja jums nav savas Dataverse vides, un mēs to izveidosim jums.

Papildinformāciju skatiet rakstā [Darbs ar Customer Insights datiem programmā Microsoft Dataverse](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="datu kopīgošana ar Microsoft Dataverse automātiski iespējotu neto jaunām vidēm.":::

### <a name="step-4-finalize-the-settings"></a>4. darbība. Iestatījumu pabeigšana

**Solī Pārskatīšana** veiciet visus norādītos iestatījumus. Kad viss izskatās pabeigts, atlasiet opciju **Izveidot**, lai iestatītu vidi.

Dažus iestatījumus vēlāk var mainīt. Papildinformācijai skatiet [Vižu pārvaldība](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Darbs ar jauno vidi

Lai palīdzētu sākt Customer Insights konfigurēšanu, pārskatiet šos rakstus:

- [Pievienojiet vairāk lietotāju un piešķiriet atļaujas](permissions.md).
- [Izgūstiet savus datu avotus](data-sources.md) un palaidiet tos [datu unificēšanas procesā](data-unification.md), lai iegūtu [vienotos klientu profilus](customer-profiles.md).
- [Bagātināt vienotos klientu profilus](enrichment-hub.md) vai [palaist prognozējošus modeļus](predictions-overview.md).
- [Izveidojiet segmentus](segments.md), lai grupētu klientus un [pasākumus](measures.md) KPI pārskatīšanai.
- [Iestatiet savienojumus](connections.md) un [eksportu](export-destinations.md), lai apstrādātu datu apakškopas citās lietojumprogrammās.

## <a name="copy-the-environment-configuration"></a>Izveidojiet vides konfigurācijas kopiju

Kā administrators varat izvēlēties kopēt konfigurāciju no esošas vides, kad izveidojat jaunu.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Vides iestatījumos redzamo iestatījumu opciju ekrānuzņēmums.":::

Jūs redzēsiet sarakstu, kurā ir visas jūsu organizācijā pieejamās vides, no kurām varat kopēt datus.

Tiek kopēti tālāk norādītie konfigurācijas iestatījumi.

- Datu avoti, kas importēti, izmantojot Power Query
- Datu apvienošanas konfigurācija
- Segmenti
- Mērījumi
- Attiecības
- Darbības
- Meklēšanas un filtrēšanas rādītājs
- Eksportēšanas darbības
- Grafika atsvaidzināšana
- Bagātinājumi
- Prognoze modeļi
- Lomu piešķiršana

## <a name="set-up-a-copied-environment"></a>Kopētas vides iestatīšana

Kopējot vides konfigurāciju, jāveic dažas papildu darbības, lai apstiprinātu akreditācijas datus:

- Klientu profili. Vispirms autentificējiet un uzņemiet savus datu avotus un palaidiet datu apvienošanu, lai atjaunotu klientu profilus.
- Datu avota akreditācijas dati. Lai autentificētu un atsvaidzinātu datu avotus manuāli, jums ir jānorāda akreditācijas dati par katru datu avots.
- Datu avoti no mapes Bieži lietotais datu modelis un Dataverse. Šie datu avoti ir jāizveido manuāli ar tādu pašu nosaukumu kā avota vidē.
- Savienojuma noslēpumi, ko izmanto eksportam un bagātināšanai. Jums ir atkārtoti jāautentificē savienojumi un pēc tam atkārtoti jāaktivizē bagātināšana un eksports.

Kad kopētā vide ir izveidota, tiks parādīts apstiprinājuma ziņojums. Atlasiet **Doties uz datu avotiem**, lai skatītu datu avotu sarakstu.

Visiem datu avotiem būs redzams statuss **Nepieciešami akreditācijas dati**. Rediģējiet datu avotus un ievadiet akreditācijas datus, lai tos atsvaidzinātu.

:::image type="content" source="media/data-sources-copied.png" alt-text="Kopēto un autentifikācijai nepieciešamo datu avotu saraksts.":::

Pēc datu avotu atsvaidzināšanas dodieties uz **Dati** > **Apvienot**. Šeit atradīsit avota vides iestatījumus. Rediģējiet tos pēc nepieciešamības vai atlasiet **Izpildīt**, lai sāktu datu unificēšanas procesu un izveidotu unificētu klienta entītiju.

Kad datu unificēšana ir pabeigta, dodieties uz **Pasākumi** un **Segmenti**, lai atsvaidzinātu arī tos.

Pirms eksportēšanas un bagātināšanas atkārtotas aktivizēšanas dodieties uz **Administrēšanas** > **savienojumi**, lai atkārtoti apstiprinātu savienojumus jaunajā vidē.

[!INCLUDE [footer-include](includes/footer-banner.md)]
