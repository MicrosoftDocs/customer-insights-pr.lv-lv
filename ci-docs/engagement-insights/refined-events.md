---
title: Notikumu izveide un modificēšana
description: Kā izveidot un modificēt notikumus.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: dbafa2231daa82c34ee2ec8292111575e95af675
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228212"
---
# <a name="create-and-modify-events"></a>Notikumu izveide un modificēšana

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Notikums ir dati, kas norāda lietotāja uzvedību, piemēram, darbību tīmekļa vietnē.

- *Pamata* notikums ieraksta, kad lietotājs skata lapu (skata notikumu) vai mijiedarbojas ar saturu (darbības notikums).
- *Precizēts* notikums ir pamata notikuma virtuāls skats. Noņemot un pievienojot rekvizītus vai filtrējot notikumus, kas balstīti uz rekvizītu vērtībām, definējat notikumus.

## <a name="prerequisites"></a>Priekšnosacījumi

Lai iegūtu notikumus, tīmekļa vietnes dati ir jāsavieno ar iesaistes ieskatiem, izmantojot vienkāršu koda fragmentu. Papildinformāciju skatiet [vietnes tīmekļa SDK instalēšana](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Vispirms savienojiet datus.":::

## <a name="create-refined-events"></a>Precizētu notikumu izveide

Izmantojiet rakstos esošos notikumus, lai samazinātu pamata notikumu tvērumu [eksportēšanai](export-events.md) vai rekvizītu noņemšanai, kas nav nepieciešams vēlamajā notikumā.

> [!NOTE]
> Kad vietnei pievienosit tīmekļa SDK, varat apskatīt pamata notikumus un izveidot rakstos notikumus. 

Lai skatītu pamata notikumus:

1. Kreisās puses navigācijas rūtī dodieties uz **Dati**.

1. Atlasiet **Notikumi**, lai skatītu visu darbvietas notikumu sarakstu.

    :::image type="content" source="media/data-events.png" alt-text="Skatīt notikumus.":::

Lai izveidotu precizētu notikumu no pamata notikuma: 

1. Dodieties uz **Dati** > **Notikumi** un ekrāna augšdaļā atlasiet **+ Jauni notikumi**.

1. Dialoglodziņā **Jauni notikumi** atlasiet **Izveidot precizētus notikumus** un pēc tam atlasiet **Tālāk**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Jaunu notikumu vednis.":::
     
1. Dialoglodziņā **Jauni notikumi** ievadiet šādu informāciju:

   - Nolaižamajā izvēlnē **Pamata notikumi** atlasiet notikumu.
   - Lodziņā **Precizēto notikumu parādāmais nosaukums** ievadiet nosaukumu.
   - Ja vēlaties, atjauniniet ieteikto **Faktisko nosaukumu**, neizmantojot atstarpes.

1. Lai lietotu iestatījumus, atlasiet vienumu **Izveidot**.

Tagad precizētais notikums tiek parādīts **Notikumu** sarakstā.

### <a name="edit-event-name"></a>Rediģēt notikuma nosaukumu

Varat mainīt pamata vai precizētā notikuma nosaukumu un rekvizītus.

1. Doties uz **Dati** > **Notikumi**. 

1. Atlasiet **Vairāk [...]** notikumam un atlasiet **Rediģēt nosaukumu**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Iespējas, lai izveidotu precizētus notikumus.":::

3. Atjauniniet notikuma nosaukumu un atlasiet **Pārdēvēt**.

### <a name="view-the-details-of-a-refined-event"></a>Skatiet detalizētu informāciju par precizētu notikumu:

1. **Notikumu** sarakstā atlasiet savu pamata vai precizēto notikumu. 

1. Lai atvērtu rūti **Rediģēt rekvizītus**, ekrāna augšdaļā atlasiet **Pievienot un noņemt rekvizītus**. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Rekvizītu pievienošana un noņemšana.":::

1. Atzīmējiet izvēles rūtiņas, lai atlasītu rekvizītus, ko vēlaties rādīt, un tos, ko vēlaties paslēpt. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Rediģēt rekvizītus precizētiem notikumiem.":::

1. Atlasiet **Apstiprināt**, lai lietotu atlasi, un pēc tam atlasiet **Saglabāt**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Rediģēt atlasītos precizētā notikuma rekvizītus

1. Dodieties uz **Dati** > **Notikumi** un atlasiet precizētos notikumus, lai atvērtu detalizēto skatu.
1. Atlasiet vienumu **Pievienot un noņemt rekvizītus**. 
1. Rediģēt izvēles rūtiņu atlasi.
1. Atlasiet **Apstiprināt** un pēc tam **Saglabāt**, lai lietotu veiktās izmaiņas.

Informāciju par notikumu eksportēšanu skatiet sadaļā [Notikumu eksportēšana](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
