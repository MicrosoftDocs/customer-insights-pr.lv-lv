---
title: Customer Insights datu eksportēšana uz Azure Data Lake Storage Gen2
description: Uzziniet, kā konfigurēt savienojumu ar Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22eee11666752459a1750d728c4e254ab0c59e58
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947239"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Segmentu saraksta un citu datu eksportēšana uz Azure Data Lake Storage Gen2 (priekšskatījums)

Glabājiet Customer Insights datus pakalpojuma Azure Data Lake Storage Gen2 kontā vai izmantojiet to, lai pārsūtītu datus uz citām programmām.

## <a name="known-limitations"></a>Zināmie ierobežojumi

1. Izmantojot Azure Data Lake Storage Gen2, varat izvēlēties starp [Standarta veiktspēju un Premium veiktspējas līmeni](/azure/storage/blobs/create-data-lake-storage-account), kad veidojat datu importēšanai paredzētu krātuves kontu. Ja izvēlaties Premium veiktspējas līmeni, atlasiet premium bloka BLOB kā uzņēmuma tipu.

## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Iestatiet savienojumu ar Azure Data Lake Storage Gen2

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Azure Data Lake Gen 2**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet **Uzņēmuma nosaukumu**, **Uzņēmuma atslēgu** un **Konteineru** jūsu Azure Data Lake Storage Gen2.
    - Informāciju par to, kā izveidot krātuves kontu, ko izmantot ar Azure Data Lake Storage Gen2, skatiet [Krātuves konta izveide](/azure/storage/blobs/create-data-lake-storage-account). 
    - Papildinformāciju par Azure Data Lake Gen2 glabāšanas konta nosaukumu un konta atslēgu skatiet rakstā [Krātuves konta iestatījumu pārvaldība Azure portālā](/azure/storage/common/storage-account-manage).

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot eksportu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas **Azure Data Lake**. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.

1. Atzīmējiet lodziņu blakus visām entītijām, ko vēlaties eksportēt šajā galamērķī.

1. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).
Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).

Eksportētie dati tiek glabāti jūsu konfigurētajā Azure Data Lake Gen 2 krātuves konteinerā.

> [!TIP]
> Eksportējot entītijas, kurās ir liels datu apjoms, katram eksportam vienā mapē var rasties vairāki CSV faili. Eksporta sadalīšana notiek veiktspējas apsvērumu dēļ, lai samazinātu laiku, kas nepieciešams eksporta pabeigšanai.

[!INCLUDE [footer-include](includes/footer-banner.md)]
