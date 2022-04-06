---
title: Programmā Customer Insights izveidotie segmenti
description: Darbības, kas jāveic, lai izveidotu vidi, izmantojot licencētu Dynamics 365 Customer Insights abonementu.
ms.date: 03/28/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: a538237322615f69f0a5cb43d394275bf79af00b
ms.sourcegitcommit: ae02ac950810242e2505d7d371b80210dc8a0777
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/29/2022
ms.locfileid: "8491922"
---
# <a name="create-an-environment-in-audience-insights"></a>Izveidot vidi auditorijas ieskatos

Šajā rakstā izskaidrots, kā izveidot jaunu vidi pēc tam, kad jūsu organizācija ir iegādājusies Dynamics 365 Customer Insights abonementu. 

Organizācijas katrai Customer Insights licencei var izveidot *divas* vides. Ja jūsu organizācija iegādājas vairāk nekā vienu licenci, [sazinieties ar mūsu atbalsta grupu](https://go.microsoft.com/fwlink/?linkid=2079641), lai palielinātu pieejamo vižu skaitu. Lai iegūtu papildinformāciju par noslodzi un pievienojumprogrammu noslodzi, lejupielādējiet [Dynamics 365 licencēšanas rokasgrāmatu](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Ja vēlaties izmēģināt pakalpojumu, skatiet sadaļu [Izmēģinājumversijas iestatīšana](../trial-signup.md).

## <a name="create-a-new-environment"></a>Jaunas vides izveide

Pēc Customer Insights abonementa licences iegādes nomnieka globālais administrators Microsoft 365 saņem e-pasta ziņojumu, kurā viņš tiek aicināts izveidot vidi. Lai sāktu, dodieties uz [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start). 

Vadītā pieredze palīdz veikt darbības, kas jāveic, lai apkopotu visu nepieciešamo informāciju par jauno vidi. Lai izveidotu vai pārvaldītu vidi, ir nepieciešamas [administratora atļaujas](permissions.md) auditorijas ieskatos.

1. Auditorijas ieskatos atveriet vides atlasītāju un atlasiet **+ Jauns**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Vides atlasītāja atlase.":::

1. Izpildiet nākamajās sadaļās norādītās vadītās iespējas.

### <a name="step-1-provide-environment-information"></a>1. darbība. Sniedziet informāciju par vidi

**Pamatinformācijas** solī izvēlieties, vai vēlaties veidot vidi, izmantojot slāpējumu, vai [kopēt datus no citas vides](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialoglodziņš jauna savienojuma izveidei ar Customer Insights.":::

Sniedziet šādu informāciju:
   - **Nosaukums**: Šīs vides nosaukums. Šis lauks jau ir aizpildīts, ja esat kopējis no esošas vides, bet varat to mainīt.
   - **Izvēlieties savu biznesu**: izvēlieties jaunās vides primāro auditoriju. Jūs varat strādāt ar individuāliem klientiem (B2C) vai [biznesa uzņēmumiem](work-with-business-accounts.md) (B2B).
   - **Veids**: Atlasiet, vai vēlaties veidot ražošanas vai smilškastes vidi. Smilškastes vidēs nevar veikt plānotu datu atsvaidzināšanu, un tās ir paredzētas iepriekšējai ieviešanai un testēšanai. Smilškastes vides izmanto to pašu primāro mērķauditoriju, kas ir pašlaik atlasītā ražošanas vide.
   - **Reģions**: Reģions, kurā tiek izvietots un viesots pakalpojums.

### <a name="step-2-configure-data-storage"></a>2. darbība. Datu krātuves konfigurēšana

**Datu krātuves** solī izvēlieties, kur glabāt datus, izmantojot auditorijas ieskatus.

Jums ir divas iespējas: **Customer Insights krātuve** (Azure Data Lake, ko pārvalda Customer Insights darba grupa) un **Azure Data Lake Storage** (jūsu pašu Azure Data Lake Storage). Pēc noklusējuma tiek atlasīta opcija Customer Insights krātuve.

:::image type="content" source="media/data-storage-environment.png" alt-text="Izvēlieties, kurā Azure Data Lake Storage glabāt auditorijas ieskatu datus.":::

Saglabājot datus Azure Data Lake Storage, jūs piekrītat, ka dati tiks pārsūtīti un glabāti attiecīgajā ģeogrāfiskā atrašanās vietā šim Azure krātuves kontam. Šī atrašanās vieta var atšķirties no tā, kur tiek glabāti Dynamics 365 Customer Insights dati. Uzziniet vairāk [Microsoft Uzticības centrs](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights pašlaik atbalsta tālāk norādītās iespējas:
> - Izgūtās entītijas no Power BI datu plūsmām, kas tiek glabātas Microsoft Dataverse pārvaldītā Data Lake.  
> - Azure Data Lake Storage konti no tā paša Azure reģiona, kas tika atlasīts vides izveides laikā.
> - Azure Data Lake Storage kontiem, kas ir Gen2 un kuriem ir *iespējota hierarhiska nosaukumvieta*. Azure Data Lake Gen1 krātuves konti netiek atbalstīti.

Programmas Azure Data Lake Storage opcijai varat izvēlēties uz resursiem balstītu opciju un uz abonēšanu balstītu autentifikācijas opciju. Papildinformāciju skatiet sadaļā [Savienojuma izveide Azure Data Lake Storage ar uzņēmumu, izmantojot Azure pakalpojuma vadītāju](connect-service-principal.md). **Konteinera** nosaukums būs `customerinsights`, un to nevar mainīt.

Kad sistēmas procesi, piemēram, datu induel izpildīšana, sistēma izveido atbilstošas mapes jūsu norādītajā krātuves kontā. Datu faili un *model.json* faili tiek izveidoti un pievienoti mapēm, pamatojoties uz procesa nosaukumu.

Ja izveidojat vairākas Customer Insights vides un vēlaties saglabāt izvades entītijas no šīm vidēm krātuves kontā, Customer Insights izveido atsevišķas mapes katrai videi, kuras saturs ir `ci_environmentID` konteiners.

### <a name="step-3-connect-to-microsoft-dataverse"></a>3. darbība. Izveidojiet savienojumu ar Microsoft Dataverse
   
Šī **Microsoft Dataverse** darbība ļauj izveidot Customer Insights savienojumu ar savu Dataverse vidi.

Nodrošiniet savu Microsoft Dataverse vidi, lai koplietotu datus (profilus un ieskatus) ar biznesa lietojumprogrammām, pamatojoties uz Dataverse, piemēram, Dynamics 365 Marketing vai modeļa vadītām lietojumprogrammām programmā Power Apps. Atstājiet šo lauku tukšu, ja jums nav savas Dataverse vides, un mēs jums to nodrošināsim.

Savienojuma izveide ar Dataverse vidi arī ļauj [uzņemt datus no lokāls datu avotiem, izmantojot Power Platform datu plūsmas un vārtejas](data-sources.md#add-data-from-on-premises-data-sources). Varat arī izmantot [gatavus prognoze modeļus](predictions-overview.md?tabs=b2c#out-of-box-models), izveidojot savienojumu ar Dataverse vidi.

> [!IMPORTANT]
> 1. Customer Insights, un Dataverse, lai iespējotu datu koplietošanu, tam jāatrodas vienā reģionā.
> 1. Jums ir jābūt globāla administratora lomai Dataverse vidē. Pārbaudiet, vai šī [Dataverse vide ir saistīta ar](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) noteiktām drošības grupām, un pārliecinieties, vai esat pievienots šīm drošības grupām.
> 1. Ar šo vidi jau nav saistīta Dataverse neviena esoša Customer Insights vide. Uzziniet, [kā noņemt esošu savienojumu ar Dataverse vidi](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="datu koplietošana ar Microsoft Dataverse automātisko iespējotu neto jaunām instancēm.":::

Papildinformāciju par datu koplietošanas iespējošanu no savas Microsoft Dataverse informācijas skatiet rakstā Azure Data Lake Storage Savienojuma izveide [ar Microsoft Dataverse](manage-environments.md#connect-to-microsoft-dataverse).

Customer Insights neatbalsta šādus datu kopīgošanas scenārijus:
- Ja iespējosit datu kopīgošanu ar Dataverse, jūs nevarēsit [izveidot paredzamas vai trūkstošas vērtības entītijā](predictions.md).

### <a name="step-4-finalize-the-settings"></a>4. darbība. Iestatījumu pabeigšana

Solī **Pārskatīšana** pārskatiet visus norādītos iestatījumus. Kad viss izskatās pabeigts, atlasiet opciju **Izveidot**, lai iestatītu vidi. 

Lielāko daļu iestatījumu varat mainīt arī vēlāk. Papildinformācijai skatiet [Vižu pārvaldība](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Darbs ar jauno vidi

Lai palīdzētu sākt Customer Insights konfigurēšanu, pārskatiet šos rakstus: 

- [Pievienojiet vairāk lietotāju un piešķiriet atļaujas](permissions.md).
- [Izgūstiet savus datu avotus](data-sources.md) un palaidiet tos [datu unificēšanas procesā](data-unification.md), lai iegūtu [vienotos klientu profilus](customer-profiles.md).
- [Bagātināt vienotos klientu profilus](enrichment-hub.md) vai [palaist prognozējošus modeļus](predictions-overview.md).
- [Izveidojiet segmentus](segments.md), lai grupētu klientus un [pasākumus](measures.md) KPI pārskatīšanai.
- [Iestatiet savienojumus](connections.md) un [eksportu](export-destinations.md), lai apstrādātu datu apakškopas citās lietojumprogrammās.
