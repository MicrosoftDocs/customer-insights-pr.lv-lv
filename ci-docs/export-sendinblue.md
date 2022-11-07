---
title: Segmentu eksportēšana uz Sendinblue (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Sendinblue.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc4ac34c1de096e25ba6c374fe17b1da6b2f745f
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724903"
---
# <a name="export-segments-to-sendinblue-preview"></a>Segmentu eksportēšana uz Sendinblue (priekšskatījums)

Eksportējiet vienotos klienta profila segmentus, lai ģenerētu kampaņas, nodrošinātu e-pasta mārketingu un izmantotu specifiskas klientu grupas pakalpojumā Sendinblue.

## <a name="prerequisites"></a>Priekšnoteikumi

- Sendinblue [konts](https://www.sendinblue.com/) un atbilstošie administratora akreditācijas dati.
- SendinBlue [API atslēga](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- Esošie Sendinblue saraksti un atbilstošie ID.
- [Konfigurēti segmenti](segments.md).
- Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Privātā saite kombinācijā ar krātuvi Bring your own storage (BYOS) netiek atbalstīta.
- Līdz 1 miljonam klientu profilu vienā eksporta reizē uz Sendinblue, kas var aizņemt līdz 90 minūtēm. Klientu profilu skaits, ko varat eksportēt uz Sendinblue, ir atkarīgs no jūsu līguma ar Sendinblue.
- Tikai segmenti.

## <a name="set-up-connection-to-sendinblue"></a>Savienojuma ar Sendinblue iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Sendinblue**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet savu **SendinBlue API atslēgu**.

1. Pārskatiet datu konfidencialitāti [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu, lai inicializētu savienojumu**.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportu**.

1. Laukam **Savienojums eksportēšanai** izvēlieties savienojumu no Sendinblue sadaļas. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. Ievadiet savu **Sendinblue saraksta ID.**

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi.

1. Pēc izvēles eksportējiet **vārds**, **uzvārds** un **tālruni**, lai izveidotu personalizētākus e-pasta ziņojumus. Atlasiet **Pievienot atribūtu**, lai kartētu šos laukus.

1. Atlasiet segmentus, kurus vēlaties eksportēt.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
