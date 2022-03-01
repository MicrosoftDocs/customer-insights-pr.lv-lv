---
title: Jaunas vides izveide
description: Vides mērķis un jaunas darbvietas izveides veids.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 5e301b4ff0a7586fb143b154b773791b3bd645b7
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648126"
---
# <a name="create-a-new-environment"></a>Jaunas vides izveide 

## <a name="overview"></a>Pārskats

Vide ir vieta, kurā pārvaldīt darbvietas un savienojumus. Vides izmantošanas veids ir atkarīgs no uzņēmuma un lietošanas gadījuma. Piemēram, varat izveidot:

- Vienu vidi.
- Atsevišķas vides testēšanai un ražošanai.
- Atsevišķas vides noteiktām organizācijas darba grupām vai departamentiem, kuros ir ietverti katrai auditorijai atbilstoši notikumi.
- Atsevišķas vides dažādiem jūsu uzņēmuma globālajām filiālēm.
- Savienojumi ar Customer Insights auditorijas ieskatu iespējām.

## <a name="create-a-new-environment"></a>Jaunas vides izveide

1. Galvenā reklāmkaroga labajā pusē atlasiet vides atlasītāju un pēc tam **+ Jauns**.

   :::image type="content" source="media/environment-picker.png" alt-text="Vides atlasītāja atlase.":::

1. **Uzstādīšanas** rūtī ierakstiet **Vides nosaukumu**.

1. Atkarībā no plāna tipa izvēlieties uzņēmuma **Veidu**.

1. Izvēlieties **Reģionu** un atlasiet **Tālāk**. 

1. Ierakstiet **Darbvietas nosaukumu**, kas ļauj apkopot datus par noteiktu vietni vai programmām. Papildinformāciju skatiet tēmā [Izveidot darbvietu](create-workspace.md).

1. Izvēlieties **Darbvietas veidu** (tīmeklis vai mobilā versija), kuru vēlaties izveidot. 

1. Atlasiet vienumu **Rādīt papildu iestatījumus**, lai iespējotu vai atspējotu šos neobligātos iestatījumus:

   - Pārslēgt **Nav zināms, ka tas ir** uz "iespējots", lai saistītu tīmekļa notikumus ar lietotājiem, kas iepriekš autentificēti. Papildinformāciju skatiet sadaļā [Tīmekļa notikumu atpazīšana no iepriekš autentificētiem apmeklētājiem](unknown-to-known.md)
   - Pārslēdziet **Filtrēt botu datplūsmu** uz "iespējota", lai noņemtu botu tīmekļa datplūsmu šai darbvietai. 

1. Kad esat beidzis, atlasiet **Pabeigt**. 

1. Instalējiet koda fragmentu, lai sāktu saņemt datus, un pēc tam atlasiet **Pabeigt**, lai izveidotu darbvietu. Lai iegūtu papildinformāciju, skatiet [Izstrādātāju resursu pārskatu](developer-resources.md).

> [!NOTE]
> Tagad sarakstā **Lomas** varat pievienot dalībniekus un piešķirt viņu atļauju līmeni. Papildinformāciju skatiet sadaļā [Lomas un atļaujas](user-roles.md). 

Papildinformāciju skatiet sadaļā [Vides un darbvietu pārvaldība](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Darbs ar jauno vidi

- [Izveidot darbvietu](../engagement-insights/create-workspace.md) un pievienot dalībniekus.
- [Pievienojiet kodu tīmekļa vietnei](../engagement-insights/instrument-website.md) vai [mobilajai programmai](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- Skatiet [reāllaika ziņojumu](../engagement-insights/view-reports.md) vai izveidojiet [pielāgotus ziņojumus](../engagement-insights/custom-reports.md).
- [Izveidojiet precizētus notikumus](../engagement-insights/refined-events.md) eksportēšanai.
- [Eksportējiet datus](../engagement-insights/export-events.md) uz Data Lake Storage.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
