---
title: Savienojuma izveide ar entītijām Common Data Service pārvaldītajā ezerā
description: Datu importēšana no Common Data Service pārvaldītā datu ezera.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267823"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Savienojuma izveide ar datiem Common Data Service pārvaldītā datu ezerā

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Šajā rakstā sniegta informācija, kā esošie Dynamics 365 klienti var ātri pieslēgties analītiskajām entitījām Common Data Service pārvaldītā ezerā. Lai turpinātu un skatītu pārvaldītajā ezerā pieejamo entītiju sarakstu, ir jābūt Common Data Service organizācijas administratoram.

## <a name="important-considerations"></a>Svarīgi ieteikumi

Dati, kas tiek glabāti tiešsaistes pakalpojumos, piemēram, Azure Data Lake Storage, var tikt glabāti citā atrašanās vietā, nevis tajā, kur dati tiek apstrādāti vai glabāti programmā Dynamics 365 Customer Insights. Importējot vai savienojot ar tiešsaistes pakalpojumos glabātajiem datiem, jūs piekrītat, ka datus var pārnest uz Dynamics 365 Customer Insights un glabāt tajā. [Papildinformāciju skatiet Microsoft drošības kontroles centrā.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Savienojuma izveide ar Common Data Service pārvaldīto datu ezeru

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.

2. Atlasiet **Pievienot datu avotu**.

3. Atlasiet opciju **Izveidot savienojumu ar Common Data Service** un atlasiet **Tālāk**.

4. Ievadiet **Nosaukumu** datu avotam un atlasiet **Tālāk**. Nosaukuma vadlīnijas: 
   - Sāciet ar burtu.
   - Izmantojiet tikai burtus un ciparus. Speciālās rakstzīmes un atstarpes nav atļautas.
   - Izmantojiet no 3 līdz 64 rakstzīmēm.

5. Norādiet **Servera adrese** jūsu Common Data Service organizācijai un atlasiet **Pierakstīties**.

   > [!div class="mx-imgBorder"]
   > ![Dialoglodziņš, lai ievadītu Common Data Service servera adresi](media/enter-CDS-org-details.png)

6. Atlasiet entītijas, ko vēlaties iegūt no pieejamo saraksta.    

   > [!NOTE]
   > Ja dažas entītijas jau ir atlasītas, iespējams, tās izmanto citas Dynamics 365 lietojumprogrammas (piemēram, Dynamics 365 Sales Insights vai Customer Service Insights). Atlasi nevar mainīt. Šīs entītijas būs pieejamas, kolīdz tiks izveidots datu avots.

   > [!div class="mx-imgBorder"]
   > ![Dialoglodziņš, kurā redzams entītiju saraksts Common Data Service organizācijā](media/select-analytical-entities.png)

7. Saglabājiet atlasi, lai sāktu atlasīto entītiju sinhronizēšanu ar Common Data Service pārvaldīto datu ezeru. Tikko izveidotais savienojums ir atrodams lapā **Datu avoti**. Tas tiks ievietots rindā atsvaidzināšanai un rādīs entītiju skaitu kā 0, līdz visas entītijas būs sinhronizētas.

Tikai vienas vides datu avots var vienlaikus izmantot to pašu Common Data Service pārvaldīto ezeru.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Common Data Service pārvaldītā datu ezera datu avota rediģēšana

Entītijas atlasi var rediģēt tikai pēc datu avota izveides. Piemēram, ja Common Data Service tika pievienotas papildu entītijas un jūs vēlaties importēt arī tās.    
Lai izveidotu savienojumu ar citu Common Data Service, [izveidojiet jaunu datu avotu](#connect-to-a-common-data-service-managed-lake).

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.

2. Blakus atjaunināmajam datu avotam atlasiet elipsi.

3. No saraksta atlasiet opciju **Rediģēt**.

4. Pieejamo entītiju sarakstā atlasiet papildu entītijas un atlasiet **Saglabāt**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]