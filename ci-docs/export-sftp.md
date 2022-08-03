---
title: Eksportējiet datus uz SFTP resursdatoriem (priekšskatījums) (satur video)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz SFTP atrašanās vietu.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207238"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Datu eksportēšana uz SFTP resursdatoriem (priekšskatījums)

Izmantojiet klientu datus trešo pušu lietojumprogrammās, eksportējot tos uz drošu failu pārsūtīšanas protokola (SFTP) atrašanās vietu.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Priekšnoteikumi

- SFTP resursdatora pieejamība un atbilstošie akreditācijas dati.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- SFTP mērķi aiz ugunsmūriem pašlaik netiek atbalstīti.
- Eksportēšanas izpildlaiks ir atkarīgs no sistēmas veiktspējas. Kā minimālu servera konfigurēšanu ieteicams izmantot divus procesora kodolus un 1 Gb atmiņu.
- Līdz 100 miljoniem klientu profilu, kas var aizņemt 90 minūtes, izmantojot ieteicamo minimālo konfigurāciju diviem CPU kodoliem un 1 Gb atmiņai.
- Ja autentifikācijai izmantojat SSH atslēgu, noteikti izveidojiet [savu privāto atslēgu](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) kā PEM vai SSH.COM formātu. Ja izmantojat špakteli, konvertējiet savu privāto atslēgu, eksportējot ir kā Open SSH. Tiek atbalstīti šādi privātās atslēgas formāti:
  - RSA OpenSSL PEM un ssh.com formātā
  - DSA OpenSSL PEM un ssh.com formātā
  - ECDSA 256/384/521 OpenSSL PEM formātā
  - ED25519 un RSA OpenSSH atslēgas formātā

## <a name="set-up-connection-to-sftp"></a>Savienojuma ar SFTP iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **SFTP**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Izvēlieties, vai vēlaties autentificēties, izmantojot SSH vai lietotājvārdu/paroli savienojumam, un norādiet nepieciešamo informāciju. Ja autentifikācijai izmantojat SSH atslēgu, noteikti izveidojiet [savu privāto atslēgu](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) kā PEM vai SSH.COM formātu. Ja izmantojat špakteli, konvertējiet savu privāto atslēgu, eksportējot ir kā Open SSH. Tiek atbalstīti šādi privātās atslēgas formāti:
   - RSA OpenSSL PEM un ssh.com formātā
   - DSA OpenSSL PEM un ssh.com formātā
   - ECDSA 256/384/521 OpenSSL PEM formātā
   - ED25519 un RSA OpenSSH atslēgas formātā

1. Atlasiet **Pārbaudīt**, lai testētu savienojumu.

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportēšanu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas SFTP. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. Izvēlieties, vai vēlaties eksportēt datus kā **Gzipped** vai **Unzipped**, un eksportēto failu **lauku norobežotāju**.

1. Atlasiet entītijas, piemēram, segmentus, kurus vēlaties eksportēt.

   > [!NOTE]
   > Eksportējot katru atlasīto entītiju, tā tiks sadalīta ne vairāk kā piecos izvades failos.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> Eksportējot entītijas, kurās ir liels datu apjoms, katrā eksportā var rasties vairāki CSV faili vienā mapē. Eksportēšanas sadalīšana notiek veiktspējas apsvērumu dēļ, lai samazinātu laiku, kas nepieciešams eksportēšanas pabeigšanai.

[!INCLUDE [footer-include](includes/footer-banner.md)]
