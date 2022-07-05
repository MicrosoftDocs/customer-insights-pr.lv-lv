---
title: Savienojuma izveide ar datiem Microsoft Dataverse pārvaldītā datu ezerā
description: Datu importēšana no Microsoft Dataverse pārvaldītā datu ezera.
ms.date: 05/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 9ae0b964d8d39835715b7ddadc712e2338b855af
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082158"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Savienojuma izveide ar datiem Microsoft Dataverse pārvaldītā datu ezerā

Microsoft Dataverse lietotāji var ātri izveidot savienojumu ar analītiskām entītijām pārvaldītā ezerā Microsoft Dataverse.

> [!NOTE]
> Jums ir jābūt organizācijas administratoram, Dataverse lai turpinātu un skatītu pārvaldītajā ezerā pieejamo entītiju sarakstu.

## <a name="important-considerations"></a>Svarīgi ieteikumi

1. Dati, kas tiek glabāti tiešsaistes pakalpojumos, piemēram, Azure Data Lake Storage, var tikt glabāti citā atrašanās vietā, nevis tajā, kur dati tiek apstrādāti vai glabāti programmā Dynamics 365 Customer Insights.Importējot vai izveidojot savienojumu ar datiem, kas tiek glabāti tiešsaistes pakalpojumos, jūs piekrītat, ka datus var pārsūtīt uz un uzglabāt kopā ar Dynamics 365 Customer Insights. [Uzziniet vairāk Microsoft drošības kontroles centrā](https://www.microsoft.com/trust-center).
2. Ir redzamas tikai Dataverse tās entītijas, kurām [ir iespējota izmaiņu izsekošana](/power-platform/admin/enable-change-tracking-control-data-synchronization). Šīs entītijas var eksportēt uz pārvaldīto Dataverse datu ezeru un izmantot programmā Customer Insights. Standarta tabulās Dataverse izmaiņu izsekošana ir iespējota pēc noklusējuma. Jums ir jāieslēdz izmaiņu izsekošana pielāgotām tabulām. Lai pārbaudītu, vai tabula ir iespējota Dataverse izmaiņu izsekošanai, dodieties uz [Power Apps](https://make.powerapps.com) > **Datu** > **tabulas**. Atrodiet sev interesējošo tabulu un atlasiet to. Dodieties uz **Papildu opciju** > **Iestatījumi** un pārskatiet **iestatījumu Izmaiņu reģistrēšana**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Savienojuma izveide ar Dataverse pārvaldīto datu ezeru

1. Dodieties uz **Dati** > **Datu avoti**.

1. Atlasiet **Pievienot datu avotu**.

1. Atlasiet **Microsoft Dataverse**.

1. **Ievadiet datu avots nosaukumu** un neobligātu **aprakstu**.

1. Norādiet **Servera adresi** Dataverse organizācijai un atlasiet **Pieteikties**.

1. Atlasiet tabulas, kuras vēlaties uzņemt kā entītijas programmā Customer Insights no pieejamā saraksta.

   > [!NOTE]
   > Ja dažas tabulas jau ir atlasītas, tās var izmantot citas Dynamics 365 lietojumprogrammas (piemēram, Dynamics 365 Sales Insights vai Customer Service Insights). Atlasi nevar mainīt. Šīs tabulas būs pieejamas kā entītijas, tiklīdz datu avots saraksts.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialoglodziņš, kurā redzams Dataverse vides entītiju saraksts.":::

1. Saglabājiet savu atlasi, lai sāktu atlasīto tabulu sinhronizēšanu no Dataverse. Tikko izveidotais savienojums ir atrodams lapā **Datu avoti**. Tā tiks ievietota rindā atsvaidzināšanai un rādīs entītiju skaitu kā 0, līdz visas atlasītās tabulas tiks sinhronizētas.

Tikai vienas vides datu avots var vienlaikus izmantot to pašu Dataverse pārvaldīto ezeru.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Dataverse pārvaldītā datu ezera datu avota rediģēšana

Entītijas atlasi var rediģēt tikai pēc datu avota izveides. Piemēram, ja Dataverse tika pievienotas papildu entītijas un jūs vēlaties importēt arī tās.
Lai izveidotu savienojumu ar citu Dataverse datu ezeru, [izveidojiet jaunu datu avotu](#connect-to-a-dataverse-managed-lake).

1. Dodieties uz **Dati** > **Datu avoti**.

1. Blakus datu avots, kuru vēlaties atjaunināt, atlasiet **Rediģēt**.

1. Pieejamo entītiju sarakstā atlasiet papildu entītijas un atlasiet **Saglabāt**.
