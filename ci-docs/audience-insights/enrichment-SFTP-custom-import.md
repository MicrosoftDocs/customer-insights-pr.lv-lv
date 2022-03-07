---
title: Bagātināšana ar SFTP pielāgoto importu
description: Vispārīga informācija par SFTP pielāgoto importēšanu.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: e4b9a65eb50f75e0243fabfc10b501cf7acf4490
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229647"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Bagātiniet klientu profilus ar pielāgotiem datiem (priekšskatījums)

Faila drošas pārsūtīšanas protokola (SFTP) pielāgotā importēšana ļauj importēt datus, kuriem nav jāiziet datu apvienošanas process. Tas ir elastīgs, drošs un viegls veids, kā apkopot datus. SFTP pielāgoto importēšanu var izmantot savienojumā ar [SFTP Export](export-sftp.md), kas ļauj eksportēt bagātināšanai nepieciešamos klientu profilu datus. Pēc tam datus var apstrādāt un bagātināt, un SFTP pielāgoto importēšanu var izmantot, lai atjaunotu bagātinātos datus ar programmas Dynamics 365 Customer Insights auditorijas ieskatiem.

## <a name="prerequisites"></a>Priekšnosacījumi

Lai konfigurētu SFTP pielāgoto importēšanu, ir jāatbilst šādiem priekšnosacījumiem:

- Jums ir faila nosaukums un atrašanās vieta (ceļš) failam, kas jāimportē SFTP resursdatorā.
- Ir *model.json* fails, kurā norādīta importējamo datu [Common Data Model shēma](/common-data-model/). Šim failam ir jābūt tajā pašā direktorijā, kur Importējamais fails.
- Administrators jau ir konfigurējis SFTP savienojumu *vai* jums ir [administratora](permissions.md#administrator) atļaujas. Jums būs nepieciešami lietotāja akreditācijas dati un STFP atrašanās vietas, no kuras vēlaties importēt datus, URL un porta numurs.


## <a name="configure-the-import"></a>Importa konfigurēšana

1. dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

1. **SFTP pielāgotās importēšanas rūtī** atlasiet **Bagātināt manus datus** un pēc tam atlasiet **Sākt darbu**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP pielāgotā importa rūts.":::

1. Atlasiet [savienojumu](connections.md) nolaižamajā sarakstā. Ja nav pieejamu savienojumu, sazinieties ar administratoru. Ja esat administrators, varat izveidot savienojumu, atlasot **Pievienot savienojumu** un izvēloties **SFTP pielāgoto importēšanu** nolaižamajā sarakstā.

1. Atlasiet **Pieslēgties Custom Import**, lai apstiprinātu atlasīto savienojumu.

1.  Atlasiet **Tālāk** un ievadiet **Ceļu** un **Faila nosaukumu** datu failam, kuru vēlaties importēt.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Ekrānuzņēmums, ievadot datu atrašanās vietu.":::

1. Atlasiet vienumu **Tālāk** un izvēlieties klientu datu kopu. Tas var būt vai nu visi klientu profili, vai segments.

1. Atlasiet **Tālāk** un norādiet bagātināmo datu nosaukumu un izvades entitījas nosaukumu. 

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt vidi**.

## <a name="configure-the-connection-for-sftp-custom-import"></a>SFTP Custom Import savienojuma konfigurēšana 

Lai konfigurētu savienojumus, jums ir jābūt administratoram. Konfigurējot bagātinātos datus, atlasiet **Pievienot savienojumu** *vai* dodieties uz **Administrators** > **Savienojumi** un Custom Import rūtī atlasiet **Iestatīt**.

1. Lodziņā **Parādāmais nosaukums** ievadiet savienojuma nosaukumu.

1. Ievadiet derīgu lietotājvārdu, paroli un resursdatora URL SFTP serverim, kurā atrodas importējamie dati.

1. Pārskatiet un sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atzīmējot izvēles rūtiņu **Piekrītu**.

1. Lai pārbaudītu konfigurāciju, atlasiet **Pārbaudīt**.

1. Kad pārbaude ir pabeigta, savienojumu var saglabāt, atlasot **Saglabāt**.

   > [!div class="mx-imgBorder"]
   > ![Experian savienojuma konfigurācijas lapa.](media/enrichment-SFTP-connection.png "Experian savienojuma konfigurācijas lapa")


## <a name="defining-field-mappings"></a>Notiek lauku kartējumu ģenerēšana 

Direktorijā, kurā ir fails, kas tiks importēts uz SFTP servera, ir jābūt iekļautam arī *model.json* failam. Šis fails definē datu importēšanai izmantojamo shēmu. Shēmai ir jāizmanto [Common Data Model](/common-data-model/), lai norādītu lauka kartējumu. Vienkāršs model.json faila piemērs izskatās šādi:

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

Lai sāktu bagātināšanas procesu, komandjoslā atlasiet **Palaist**. Varat arī ļaut sistēmai palaist bagātināšanu automātiski kā daļu no [plānotās atsvaidzināšanas](system.md#schedule-tab). Apstrādes laiks būs atkarīgs no importējamo datu apjoma un savienojuma ar SFTP serveri.

Pēc bagātināšanas procesa pabeigšanas varat pārskatīt jūsu tikko importētos pielāgotos datus par bagātināšanu zem **Manas bagātināšanas**. Turklāt jūs redzēsit pēdējā atjauninājuma laiku un bagātināto profilu skaitu.

Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
