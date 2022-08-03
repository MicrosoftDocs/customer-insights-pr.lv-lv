---
title: Segmentu eksportēšana uz LiveRamp (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196725"
---
# <a name="export-segments-to-liverampreg-preview"></a>Segmentu eksportēšana uz LiveRamp&reg; (priekšskatījums)

Aktivizējiet savus datus LiveRamp, lai savienotos ar vairāk nekā 500 digitālajām, sociālajām un TV platformām. Strādājiet ar saviem datiem risinājumā LiveRamp, lai mērķētu, izlaistu un personalizētu reklāmas kampaņas.

## <a name="prerequisites"></a>Priekšnoteikumi

- LiveRamp abonements, lai izmantotu šo savienotāju. Lai iegūtu abonementu, [sazinieties tieši ar LiveRamp](https://liveramp.com/contact/). [Uzzināt vairāk par LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Zināmie ierobežojumi

- LiveRamp eksportēšana izmanto SFTP eksportu. SFTP mērķi aiz ugunsmūriem pašlaik netiek atbalstīti.
- Ja autentifikācijai izmantojat SSH atslēgu, noteikti izveidojiet [savu privāto atslēgu](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) kā PEM vai SSH.COM formātu. Ja izmantojat špakteli, konvertējiet savu privāto atslēgu, eksportējot ir kā Open SSH. Tiek atbalstīti šādi privātās atslēgas formāti:
  - RSA OpenSSL PEM un ssh.com formātā
  - DSA OpenSSL PEM un ssh.com formātā
  - ECDSA 256/384/521 OpenSSL PEM formātā
  - ED25519 un RSA OpenSSH atslēgas formātā
- Eksportēšanas izpildlaiks ir atkarīgs no sistēmas veiktspējas. Kā minimālu servera konfigurēšanu ieteicams izmantot divus procesora kodolus un 1 Gb atmiņu.
- Līdz pat 100 miljoniem klientu profilu entītiju eksportēšana var aizņemt 90 minūtes, ja tiek izmantota ieteicama minimālā divu procesoru kodolu konfigurācija un 1 Gb atmiņa.
- Faktiskais profilu (vai datu) skaits, ko varat eksportēt uz LiveRamp, ir atkarīgs no jūsu abonementa ar LiveRamp.

## <a name="set-up-connection-to-liveramp"></a>Savienojuma ar LiveRamp iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **LiveRamp**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Izvēlieties, vai vēlaties autentificēties, izmantojot SSH vai lietotājvārdu/paroli savienojumam, un norādiet nepieciešamo informāciju.

1. Atlasiet **Pārbaudīt**, lai pārbaudītu savienojumu ar LiveRamp.

1. Pēc veiksmīgas verifikācijas pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportēšanu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas LiveRamp. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. **Laukā Savienot datus** atlasiet **E-pasts**, **Vārds un adrese** vai **Tālrunis**, ko nosūtīt uz LiveRamp identitātes atrisināšanai.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="LiveRamp savienotājs ar atribūtu kartējumu.":::

1. Kartējiet atlasītajam atslēgas identifikatoram atbilstošos atribūtus no entītijas *Klients*.

1. Atlasiet **Pievienot atribūtu**, lai kartētu vairāk atribūtu, ko nosūtīt uz LiveRamp.

   > [!TIP]
   > Vairāku galveno identifikatora atribūtu nosūtīšana uz LiveRamp, visticamāk, iegūs lielāku atbilstību.

1. Atlasiet segmentus, kurus vēlaties eksportēt.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
