---
title: Izveidot savienojumu ar tabulām programmā Microsoft Dataverse
description: Datu importēšana no Microsoft Dataverse pārvaldītā datu ezera.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: c470956b0453ac2558ed85acdeebba120a0ca55d
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011712"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Savienojuma izveide ar datiem Microsoft Dataverse pārvaldītā datu ezerā

Microsoft Dataverse lietotāji var ātri izveidot savienojumu ar analītiskām vienībām pārvaldītā Microsoft Dataverse ezerā.

> [!NOTE]
> Lai turpinātu un skatītu pārvaldītajā ezerā pieejamo entītiju sarakstu, Dataverse jums jābūt organizācijas administratoram.

## <a name="important-considerations"></a>Svarīgi ieteikumi

1. Dati, kas tiek glabāti tiešsaistes pakalpojumos, piemēram, Azure Data Lake Storage, var tikt glabāti citā atrašanās vietā, nevis tajā, kur dati tiek apstrādāti vai glabāti programmā Dynamics 365 Customer Insights.Importējot tiešsaistes pakalpojumos saglabātos datus vai izveidojot savienojumu ar Dynamics 365 Customer Insights  [tiem, jūs piekrītat, ka datus var pārsūtīt uz . Uzziniet vairāk Microsoft drošības kontroles centrā](https://www.microsoft.com/trust-center).
2. Ir redzamas tikai Dataverse tās entītijas, kurām [ir iespējota izmaiņu izsekošana](/power-platform/admin/enable-change-tracking-control-data-synchronization). Šīs entītijas var eksportēt uz pārvaldīto Dataverse datu ezeru un izmantot customer insights. Izejošajās tabulās Dataverse pēc noklusējuma ir iespējota izmaiņu izsekošana. Pielāgotām tabulām ir jāieslēdz izmaiņu izsekošana. Lai pārbaudītu, vai tabula ir iespējota Dataverse izmaiņu izsekošanai, dodieties uz [Power Apps](https://make.powerapps.com) > **Datu** > **tabulas**. Atrodiet sev interesējošo tabulu un atlasiet to. Dodieties uz **iestatījumu papildu opcijas** > **un pārskatiet** iestatījumu Reģistrēt **izmaiņas**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Savienojuma izveide ar Dataverse pārvaldīto datu ezeru

1. Dodieties uz **Dati** > **Datu avoti**.

1. Atlasiet **Pievienot datu avotu**.

1. Atlasiet **Microsoft Dataverse**.

1. **Ievadiet datu avots nosaukumu** un neobligātu **aprakstu**.

1. Norādiet **Servera adresi** Dataverse organizācijai un atlasiet **Pieteikties**.

1. Pieejamajā sarakstā atlasiet tabulas, kuras vēlaties uzņemt kā customer insights entītijas.

   > [!NOTE]
   > Ja dažas tabulas jau ir atlasītas, tās var izmantot citas Dynamics 365 lietojumprogrammas (piemēram, Dynamics 365 Sales Insights vai Customer Service Insights). Atlasi nevar mainīt. Šīs tabulas būs pieejamas kā entītijas, tiklīdz datu avots saraksts.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialoglodziņš, kurā redzams Dataverse vides entītiju saraksts.":::

1. Saglabājiet savu atlasi, lai sāktu atlasīto tabulu sinhronizēšanu no Dataverse. Tikko izveidotais savienojums ir atrodams lapā **Datu avoti**. Tā tiks ievietota rindā atsvaidzināšanai un rādīs entītiju skaitu kā 0, līdz visas atlasītās tabulas tiks sinhronizētas.

Tikai vienas vides datu avots var vienlaikus izmantot to pašu Dataverse pārvaldīto ezeru.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Dataverse pārvaldītā datu ezera datu avota rediģēšana

Entītijas atlasi var rediģēt tikai pēc datu avota izveides. Piemēram, ja Dataverse tika pievienotas papildu entītijas un jūs vēlaties importēt arī tās.
Lai izveidotu savienojumu ar citu Dataverse datu ezeru, [izveidojiet jaunu datu avotu](#connect-to-a-dataverse-managed-lake).

1. Dodieties uz **Dati** > **Datu avoti**.

1. Blakus datu avots kuru vēlaties atjaunināt, atlasiet **Rediģēt**.

1. Pieejamo entītiju sarakstā atlasiet papildu entītijas un atlasiet **Saglabāt**.
