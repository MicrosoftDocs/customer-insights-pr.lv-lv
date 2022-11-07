---
title: Segmentu eksportēšana uz Constant Contact (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Constant Contact.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c0affd3ed45f462696850813bd50331061dde780
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724510"
---
# <a name="export-segments-to-constant-contact-preview"></a>Segmentu eksportēšana uz Constant Contact (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz Constant Contact un izmantojiet tos mārketinga darbībās.

## <a name="prerequisites"></a>Priekšnoteikumi

- Pastāvīgas kontaktpersonas [konts](https://www.constantcontact.com/account-home) un atbilstošie administratora akreditācijas dati.
- Pastāvīga [kontaktpersonu saraksta ID](https://app.constantcontact.com/pages/contacts/ui#lists). Constant Contact atveriet sarakstu, lai URL vietrādī atrastu saraksta ID.
- [Konfigurēti segmenti](segments.md) programmā Customer Insights.
- Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Privātā saite kombinācijā ar krātuvi Bring your own storage (BYOS) netiek atbalstīta.
- Līdz 1 miljonam klientu profilu vienā eksportēšanā uz Constant Contact, kuru pabeigšana var aizņemt līdz pat vienai stundai. Klientu profilu skaits, ko varat eksportēt uz Constant Contact, ir atkarīgs no jūsu līguma ar Constant Contact.
- Tikai segmenti.

## <a name="set-up-connection-to-constant-contact"></a>Savienojuma ar Constant Contact izveide

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Pastāvīga kontaktpersona**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pārskatiet datu konfidencialitāti [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu, lai inicializētu savienojumu**.

1. Atlasiet vienumu **Autentificēties ar pastāvīgo kontaktpersonu** un norādiet savus administratora akreditācijas datus.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Constant Contact. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. Ievadiet pastāvīgā **kontaktpersonu saraksta ID.**

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi.

1. Pēc izvēles eksportējiet **vārds** un **uzvārds** kā papildu laukus, lai izveidotu personalizētākus e-pasta ziņojumus. Atlasiet **Pievienot atribūtu**, lai kartētu šos laukus.

1. Atlasiet segmentus, kurus vēlaties eksportēt.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
