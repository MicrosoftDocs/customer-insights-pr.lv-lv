---
title: Precizētu notikumu izveide un modificēšana
description: Kā izveidot un modificēt precizētus notikumus.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034783"
---
# <a name="create-and-modify-refined-events"></a>Precizētu notikumu izveide un modificēšana

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Notikums ir dati, kas norāda lietotāja uzvedību, piemēram, darbību tīmekļa vietnē.

- *Pamata* notikums ieraksta, kad lietotājs skata lapu (skata notikumu) vai mijiedarbojas ar saturu (darbības notikums).
- *Precizēts* notikums ir pamata notikuma virtuāls skats. Noņemot un pievienojot rekvizītus vai filtrējot notikumus, kas balstīti uz rekvizītu vērtībām, definējat notikumus.

Izmantojiet rakstos esošos notikumus, lai samazinātu pamata notikumu tvērumu [eksportēšanai](export-events.md) vai rekvizītu noņemšanai, kas nav nepieciešams vēlamajā notikumā.

## <a name="create-refined-events"></a>Izsmalcinātu notikumu izveide

Ir trīs veidi, kā no pamata notikuma izveidot precizētu notikumu. 

1. Dodieties uz **Dati**> **Notikumi** un izvēlieties kādu no šīm opcijām:
    - Atlasiet **Jauni notikumi** un pēc tam atlasiet **Izveidot precizētus notikumus**.
    - Atlasiet pamata notikumu, lai atvērtu detalizētu skatu un augšējā izvēlnē atlasiet vienumu **Izveidot precizētus notikumus**.
    - Atlasiet **Vairāk [...]**, lai atvērtu pamata notikuma īsinājumizvēlni. Pēc tam atlasiet opciju **Izveidot precizētus notikumus**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Iespējas, lai izveidotu precizētus notikumus.":::

1. Dialoglodziņā **Izveidot precizētus notikumus** ievadiet tālāk minēto informāciju.

- Ja veidojat jaunu notikumu, nolaižamajā izvēlnē **Pamata notikumi** atlasiet notikumu.
- Lodziņā **Precizēto notikumu parādāmais nosaukums** ievadiet nosaukumu.
- Ja vēlaties, atjauniniet ieteikto **Faktisko nosaukumu**, neizmantojot atstarpes.

3. Lai lietotu iestatījumus, atlasiet vienumu **Izveidot**.

1. Detalizētajā skatā par precizētajiem notikumiem, atlasiet vienumu **Pievienot un noņemt rekvizītus**, lai atvērtu rūti **Rediģēt rekvizītus**. 

1. Atzīmējiet izvēles rūtiņas, lai atlasītu rekvizītus, ko vēlaties rādīt, un tos, ko vēlaties paslēpt. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Rediģēt rekvizītus precizētiem notikumiem.":::

1. Atlasiet vienumu **Apstiprināt**, lai lietotu jūsu izvēli.

1. Atlasiet **Saglabāt**, lai saglabātu konfigurāciju.

## <a name="edit-refined-events"></a>Precizētu notikumu rediģēšana

Varat mainīt precizētā notikuma nosaukumu un rekvizītus.

### <a name="edit-event-name"></a>Rediģēt notikuma nosaukumu

1. Doties uz **Dati** > **Notikumi**. 
1. Atlasiet **Vairāk [...]** notikumam un atlasiet **Rediģēt nosaukumu**.
1. Atjauniniet notikuma nosaukumu un atlasiet **Pārdēvēt**.

### <a name="edit-selected-properties"></a>Rediģēt atlasītos rekvizītus

1. Dodieties uz **Dati** > **Notikumi** un atlasiet precizētos notikumus, lai atvērtu detalizēto skatu.
1. Atlasiet vienumu **Pievienot un noņemt rekvizītus**. 
1. Rediģēt izvēles rūtiņu atlasi.
1. Atlasiet **Apstiprināt** un pēc tam **Saglabāt**, lai lietotu veiktās izmaiņas.

Informāciju par notikumu eksportēšanu skatiet sadaļā [Notikumu eksportēšana](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
