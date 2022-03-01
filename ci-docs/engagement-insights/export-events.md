---
title: Precizētu notikumu eksportēšana
description: Kā eksportēt precizētus notikumus un pamata notikumus.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032394"
---
# <a name="export-events"></a>Notikumu eksportēšana

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Notikums norāda lietotāja uzvedību. Tas ieraksta, kad lietotājs skata lapu (skata notikumu) vai mijiedarbojas ar saturu (darbības notikums). Kad izlemjat, kādus datu rekvizītus vēlaties parādīt atskaitē, šis datu virtuālais skats tiek saukts par *precizētu notikumu*. 

- Notikumus un precizētus notikumus var eksportēt uz ārēju krātuvi. 
- Eksportēšana ir pārsūtīšanas datu straume. Straumi nevar atkārtoti aizpildīt. 
- Eksportēšanai ir fiksētas shēmas. Ja notikumam pievienosit pielāgotus rekvizītus, tie netiks iekļauti. Jums ir jāizveido jauna eksportēšana.

## <a name="prerequisites"></a>Priekšnosacījumi

Pirms eksportēšanas iestatīšanas jums ir nepieciešama piekļuve Azure portālam un aktīvs abonements. Eksportēšanas laikā jums būs nepieciešama krātuves konta informācija. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Izveidot Azure Data Lake Storage Gen 2 kontus

1. Piesakieties Azure portālā un [izveidojiet jaunu krātuves kontu](/azure/storage/common/storage-account-create). 

1. Pārliecinieties, vai cilnē **Papildus** ir iespējota **Hierarhiska nosaukumvieta**. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Iespējot hierarhisku nosaukumvietu papildus cilnē.":::

1. Kad tas ir izvietots, atveriet jaunizveidoto krātuves kontu. Navigācijas rūtī atlasiet **Iestatījumi** > **Piekļuves atslēgas**. 

1. Kopējiet **Konta nosaukumu** un **Atslēgu**, lai tos izmantotu, veidojot jaunu eksportēšanu.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Piekļuves atslēgas krātuves kontā.":::

## <a name="export-events"></a>Notikumu eksportēšana

Pastāv divi meklēšanas veidi notikumu eksportēšanai: 
- Dodieties uz **Dati** > **Eksportēšanas** un atlasiet **Jauna eksportēšana**.
- Dodieties uz **Dati** > **Notikumi**, pēc tam atlasiet **Vairāk [...]** blakus notikumam, kuru vēlaties eksportēt, un atlasiet **Eksportēt** nolaižamajā sarakstā. 

Lai izveidotu eksportēšanu, ir jāveic tālāk norādītās darbības:

1. Norādiet **Eksportēšanas nosaukumu**.

1. Nolaižamā saraksta opcijā **Notikumu atlase** izvēlieties pamatnotikumus un precizētus notikumus, ko iekļaut eksportēšanai. 

1. Sadaļā **Failu struktūra** atlasiet vietu, kurā veidot jaunus failus mērķa krātuvē. Kad tie pienāk, notikumi tiek nepārtraukti eksportēti.

1. Atlasiet eksportēšanas formātu. Varat izvēlēties starp **Common Data Model**, **CSV** un **JSON** formātu. Lai izmantotu eksportēšanu ar citām Dynamics 365 lietojumprogrammām, ieteicams izmantot Common Data Model formātu.

1. **Izvēlieties galamērķi** solī precizējiet Azure Data Lake Storage Gen 2 atrašanās vietu.
    1. **ADLS Gen 2 konta nosaukums** ir tās krātuves konta nosaukums, kurā vēlaties saglabāt šo eksportēšanu. 
    1. **Mapes ceļš** definē, kur eksportēšana jāsaglabā krātuves konta failu sistēmā un direktoriju struktūrā.
    1. **Kopīgotā atslēga** ir pieejama Azure krātuves konta portālā.

1. Pārskatiet un apstipriniet atlasi.

## <a name="view-and-manage-exports"></a>Skatīt un pārvaldīt eksportēšanas

Kad esat iestatījis eksportēšanu, atveriet sadaļu **Dati** > **Eksportēšanas**, lai to skatītu. Atlasiet **Vairāk [...]** jebkurai esošai eksportēšanai, lai to rediģētu vai dzēstu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]