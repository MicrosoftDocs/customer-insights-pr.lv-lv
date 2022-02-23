---
title: Izveidot savienojumu ar tabulām programmā Microsoft Dataverse
description: Datu importēšana no Microsoft Dataverse pārvaldītā datu ezera.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: 436345d8932820eb4c517a9e9164b1377c1f62d3
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046434"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Savienojuma izveide ar datiem Microsoft Dataverse pārvaldītā datu ezerā



Šajā rakstā ir sniegta informācija par to, kā Dataverse lietotāji var ātri izveidot savienojumu ar analītiskām vienībām apsaimniekotā Microsoft Dataverse ezerā. 

> [!NOTE]
> Lai turpinātu un skatītu pārvaldītajā ezerā pieejamo entītiju sarakstu, jums jābūt organizācijas administratoram Dataverse.

## <a name="important-considerations"></a>Svarīgi ieteikumi

Dati, kas tiek glabāti tiešsaistes pakalpojumos, piemēram, Azure Data Lake Storage, var tikt glabāti citā atrašanās vietā, nevis tajā, kur dati tiek apstrādāti vai glabāti programmā Dynamics 365 Customer Insights.Importējot tiešsaistes pakalpojumos glabātos datus vai izveidojot savienojumu ar Dynamics 365 Customer Insights tiem, jūs piekrītat, ka datus var pārsūtīt uz . [Uzziniet vairāk Microsoft drošības kontroles centrā](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-dataverse-managed-lake"></a>Savienojuma izveide ar Dataverse pārvaldīto datu ezeru

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.

2. Atlasiet **Pievienot datu avotu**.

3. Atlasiet **Microsoft Dataverse** un atlasiet **Tālāk**.

4. Ievadiet **Nosaukumu** datu avotam un atlasiet **Tālāk**. 

5. Norādiet **Servera adresi** Dataverse organizācijai un atlasiet **Pieteikties**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Ekrāns datu uzņemšanā, kur lietotājs var ievadīt Dataverse vides URL.":::

6. Pieejamā sarakstā atlasiet tabulas, kuras vēlaties izmantot kā entītijas ar auditorijas ieskatiem.    

   > [!NOTE]
   > Ja dažas tabulas jau ir atlasītas, tās var izmantot citas Dynamics 365 lietojumprogrammas (piemēram, Dynamics 365 Sales Insights vai Customer Service Insights). Atlasi nevar mainīt. Šīs tabulas būs pieejamas kā entītijas, tiklīdz datu avots saraksts.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialoglodziņš, kurā redzams Dataverse vides entītiju saraksts.":::

7. Saglabājiet savu atlasi, lai sāktu atlasīto tabulu sinhronizēšanu no Dataverse. Tikko izveidotais savienojums ir atrodams lapā **Datu avoti**. Tā tiks ievietota rindā atsvaidzināšanai un rādīs entītiju skaitu kā 0, līdz visas atlasītās tabulas tiks sinhronizētas.

Tikai vienas vides datu avots var vienlaikus izmantot to pašu Dataverse pārvaldīto ezeru.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Dataverse pārvaldītā datu ezera datu avota rediģēšana

Entītijas atlasi var rediģēt tikai pēc datu avota izveides. Piemēram, ja Dataverse tika pievienotas papildu entītijas un jūs vēlaties importēt arī tās.    
Lai izveidotu savienojumu ar citu Dataverse datu ezeru, [izveidojiet jaunu datu avotu](#connect-to-a-dataverse-managed-lake).

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.

2. Blakus atjaunināmajam datu avotam atlasiet elipsi.

3. No saraksta atlasiet opciju **Rediģēt**.

4. Pieejamo entītiju sarakstā atlasiet papildu entītijas un atlasiet **Saglabāt**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
