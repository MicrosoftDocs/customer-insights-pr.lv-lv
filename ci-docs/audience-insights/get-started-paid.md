---
title: Customer Insights apmaksātas licences izveide un konfigurēšana
description: Darbības, kas jāveic, lai iegūtu licencētu Dynamics 365 Customer Insights abonementu un to konfigurētu.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034461"
---
# <a name="get-started-with-a-paid-subscription"></a>Darba sākšana ar apmaksātu abonementu

Šajā rakstā izskaidrots, kā izveidot jaunu vidi pēc tam, kad jūsu organizācija ir iegādājusies Dynamics 365 Customer Insights abonementu. Ja vēlaties iegādāties Customer Insights, mūsu saziņas opcijas ir norādītas [Dynamics 365 Customer Insights vietnē](https://dynamics.microsoft.com/ai/customer-insights/). 

Ja vēlaties izmēģināt pakalpojumu un līdzekļus, skatiet sadaļu [Izmēģinājumversijas iestatīšana](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Vides izveide esošā organizācijā

Pēc Customer Insights abonementa licences iegādes Microsoft 365 nomnieka globālais administrators saņem e-pasta ziņojumu, kas viņiem uzaicina izveidot vidi. Lai sāktu, dodieties uz [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start). 

Customer Insights nav licencēts katram lietotājam, tāpēc tas netiks rādīts licenču apgabalā. Ja meklējat licenci Microsoft 365 administrēšanas centrā, atveriet sadaļu **Jūsu produkti**. 

> [!NOTE]
> Organizācijas katrai Customer Insights licencei var izveidot *divas* vides. Ja jūsu organizācija iegādājas vairāk nekā vienu licenci, [sazinieties ar mūsu atbalsta komandu](https://go.microsoft.com/fwlink/?linkid=2079641), lai tiktu paaugstināts pieejamo vižu skaists. Lai iegūtu papildinformāciju par noslodzi un pievienojumprogrammu noslodzi, lejupielādējiet [Dynamics 365 licencēšanas rokasgrāmatu](https://go.microsoft.com/fwlink/?LinkId=866544).

Lai izveidotu vidi:

1. Dialoglodziņā **Vides izveide** atlasiet **Jauna vide**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialoglodziņš jauna savienojuma izveidei ar Customer Insights.":::

   Ieteicams sākt vides iestatīšanu no tukšas veidlapas. Tomēr, ja esat izmēģinājumversijas administrators vai dalībnieks, datus var [kopēt no citas vides](manage-environments.md#copy-the-environment-configuration), izvēloties **Kopēt no esošas vides**. Jūs redzēsiet sarakstu, kurā ir visas jūsu organizācijā pieejamās vides, no kurām varat kopēt datus.

1. Sniedziet šādu informāciju:
   - **Nosaukums**: Šīs vides nosaukums. Šis lauks jau ir aizpildīts, ja esat kopējis no esošas vides, bet varat to mainīt.
   - **Reģions**: Reģions, kurā tiek izvietots un viesots pakalpojums.
   - **Veids**: Atlasiet, vai vēlaties veidot ražošanas vai smilškastes vidi. Smilškastes vidēs nevar veikt plānotu datu atsvaidzināšanu, un tās ir paredzētas iepriekšējai ieviešanai un testēšanai.
   
1. Pēc izvēles varat arī atlasīt **Papildu iestatījumus**:

   - **Saglabāt visus datus uz** : Norāda, kur saglabāt no Customer Insights ģenerētos izvades datus. Jums ir divas iespējas: **Customer Insights krātuve** (Azure Data Lake, ko pārvalda Customer Insights darba grupa) un **Azure Data Lake Storage** (jūsu pārvaldīta Azure Data Lake Storage). Pēc noklusējuma tiek atlasīta opcija Customer Insights krātuve.

     > [!NOTE]
     > Saglabājot datus Azure Data Lake Storage, jūs piekrītat, ka dati tiks pārsūtīti uz un uzglabāti šī Azure krātuves konta atbilstošajā ģeogrāfiskajā atrašanās vietā, kas var atšķirties no vietas, kur dati tiek glabāti programmā Dynamics 365 Customer Insights. [Uzziniet vairāk Microsoft Trust Center.](https://www.microsoft.com/trust-center)
     >
     > Pašlaik Power BI datplūsmu pārņemtās entītijas vienmēr tiek glabātas Microsoft Dataverse pārvaldītajā Data Lake. 
     > 
     > Mēs atbalstām tikai Azure Data Lake Storage kontus, kuri ir no tā paša Azure reģiona, kurš tika atlasīts vides izveides laikā. 
     > 
     > Mēs atbalstām tikai tos Azure Data Lake Storage kontus, kuriem ir iespējota hierarhiska nosaukumvieta.


   - Programmas Azure Data Lake Storage opcijai varat izvēlēties uz resursiem balstītu opciju un uz abonēšanu balstītu autentifikācijas opciju. Papildinformāciju skatiet tēmā [Auditorijas ieskatu savienošana ar Azure Data Lake Storage Gen2 kontu, izmantojot Azure pakalpojuma primāro nosaukumu](connect-service-principal.md). **Konteinera** nosaukumu nevar mainīt, un tas būs `customerinsights`.
   
   - Ja vēlaties izmantot [iepriekš izmantotus modeļus](predictions-overview.md#out-of-box-models), konfigurēt datu kopīgošanu ar Microsoft Dataverse vai iespējot datu pārņemšanu no lokālajiem datu avotiem, nodrošiniet Microsoft Dataverse vides URL sadaļā **Konfigurēt datu kopīgošanu ar Microsoft Dataverse un iespējot papildu iespējas**. Atlasiet opciju **Iespējot datu kopīgošanu**, lai kopīgotu Customer Insights izvades datus ar programmas Microsoft Dataverse pārvaldīto Data Lake.

     > [!NOTE]
     > - Datu kopīgošana ar programmas Microsoft Dataverse pārvaldīto Data Lake pašlaik netiek atbalstīta, saglabājot visus savus datus jūsu Azure Data Lake Storage.
     > - [Entītijā trūkstošo vērtību prognozēšana](predictions.md) pašlaik netiek atbalstīta, ja iespējojat datu kopīgošanu ar programmas Microsoft Dataverse pārvaldīto Data Lake.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Konfigurēšanas opcijas, lai iespējotu datu kopīgošanu ar Microsoft Dataverse.":::

   Kad sistēmas process, piemēram, datu izgūšana, ir pabeigts, sistēma izveido atbilstošas mapes jūsu norādītajā krātuves kontā. Datu faili un model.json faili tiek izveidoti un pievienoti mapēm, pamatojoties uz procesa nosaukumu.

   Ja izveidojat vairāku veidu Customer Insights un izvēlaties saglabāt izvades entītijas, izmantojot savas krātuves konta vides, katrai videi, kurai ir ci_ konteinerā, tiks izveidotas atsevišķas mapes <environmentid>.

1. Lai iestatītu vidi, atlasiet **Izveidot**. 

## <a name="configure-an-environment"></a>Vides konfigurēšana

Lai palīdzētu sākt Customer Insights konfigurēšanu, pārskatiet tālāk norādītos rakstus. 

- [Pievienojiet vairāk lietotāju un piešķiriet atļaujas](permissions.md).
- [Izgūstiet savus datu avotus](data-sources.md) un palaidiet tos [datu unificēšanas procesā](data-unification.md), lai iegūtu [vienotos klientu profilus](customer-profiles.md).
- [Bagātināt vienotos klientu profilus](enrichment-hub.md) vai [palaist prognozējošus modeļus](predictions-overview.md).
- Izveidojiet [segmentus](segments.md), lai grupētu klientus un [pasākumus](measures.md) KPI pārskatīšanai.
- Iestatiet [savienojumus](connections.md) un [eksportu](export-destinations.md), lai apstrādātu datu apakškopas citās lietojumprogrammās.
