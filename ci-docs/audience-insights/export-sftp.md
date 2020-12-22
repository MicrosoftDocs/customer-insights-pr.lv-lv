---
title: Customer Insights datu eksportēšana uz SFTP resursdatoriem
description: Uzziniet, kā konfigurēt savienojumu ar SFTP resursdatoru.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643512"
---
# <a name="connector-for-sftp-preview"></a>SFTP savienotājs (priekšskatījums)

Izmantojiet klienta datus trešo pušu lietojumprogrammās, eksportējot tos caur mūsu Drošo failu pārsūtīšanas protokola (SFTP) resursdatoru.

## <a name="prerequisites"></a>Priekšnosacījumi

- SFTP resursdatora pieejamība un atbilstošie akreditācijas dati.

## <a name="connect-to-sftp"></a>Izveidot savienojumu ar SFTP

1. Dodieties uz sadaļu **Administrators** > **Eksportēšanas galamērķi**.

1. Sadaļā **SFTP** atlasiet **Iestatīt**.

1. Laukā **Parādāmais nosaukums** piešķiriet galamērķim atpazīstamu nosaukumu.

1. Norādiet **Lietotājvārdu**, **Paroli** un **Resurdatora nosaukumu** savam SFTP kontam. Piemērs: ja jūsu SFTP servera saknes mape ir/root/folder, un jūs vēlaties, lai dati tiktu eksportēti uz/root/Folder/ci_export_destination_folder, tad viesotājam vajadzētu būt SFTP://< server_address >/ci_export_destination_folder ".

1. Atlasiet **Pārbaudīt**, lai testētu savienojumu.

1. Pēc sekmīgas pārbaudes izvēlieties, vai vēlaties eksportēt datus **Saspiestus** vai **Atspiestus**, un atlasiet eksportēto failu **Lauku norobežotāju**.

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Lai sāktu eksporta konfigurēšanu, atlasiet **Tālāk**.

## <a name="configure-the-connection"></a>Savienojuma konfigurēšana

1. Atlasiet tos **klienta atribūtus**, kurus vēlaties eksportēt. Varat eksportēt vienu vai vairākus atribūtus.

1. Atlasiet **Tālāk**.

1. Atlasiet segmentus, kurus vēlaties eksportēt.

1. Atlasiet vienumu **Saglabāt**.

## <a name="export-the-data"></a>Datu eksportēšana

Datus var [eksportēt pēc pieprasījuma](export-destinations.md). Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu caur SFTP, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu eksporta galamērķa atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.
