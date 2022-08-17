---
title: Bagātiniet klientu profilus ar SFTP pielāgotu importēšanu (priekšskatījums)
description: Vispārīga informācija par SFTP pielāgoto importēšanu.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 831d1d3d3045379bbc5bcdcd4b05b8a147221f31
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237775"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Bagātiniet klientu profilus ar SFTP pielāgotu importēšanu (priekšskatījums)

Faila drošas pārsūtīšanas protokola (SFTP) pielāgotā importēšana ļauj importēt datus, kuriem nav jāiziet datu apvienošanas process. Tas ir elastīgs, drošs un viegls veids, kā apkopot datus. SFTP pielāgoto importēšanu var izmantot savienojumā ar [SFTP Export](export-sftp.md), kas ļauj eksportēt bagātināšanai nepieciešamos klientu profilu datus. Pēc tam datus var apstrādāt un bagātināt, un SFTP pielāgoto importēšanu var izmantot, lai bagātinātos datus atgrieztu atpakaļ uz Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Priekšnoteikumi

- Faila nosaukums un SFTP resursdatorā importējamā faila atrašanās vieta (ceļš) ir zināms.

- Ir *pieejams model.json* fails, kas norāda importējamo datu kopējā datu modeļa shēmu. Šim failam ir jābūt tajā pašā direktorijā, kur Importējamais fails.

- Ir konfigurēts SFTP [savienojums](connections.md)[...](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Failu shēmas piemērs

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>SFTP Custom Import savienojuma konfigurēšana

Jums ir jābūt customer insights [administratoram](permissions.md#admin), un jums ir jābūt lietotāja akreditācijas datiem, URL un porta numuram SFTP atrašanās vietā, no kuras vēlaties importēt datus.

1. Atlasiet **Pievienot savienojumu**, konfigurējot bagātināšanu, vai dodieties uz **Administratoru** > **savienojumi** un elementā Pielāgota importēšana atlasiet **Iestatīt**.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Pielāgota savienojuma importēšanas konfigurācijas lapa.":::

1. Ievadiet savienojuma nosaukumu.

1. Ievadiet derīgu lietotājvārdu, paroli un resursdatora URL SFTP serverim, kurā atrodas importējamie dati.

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Verificēt**, lai validētu konfigurāciju, un pēc tam atlasiet **Saglabāt**.

## <a name="configure-the-import"></a>Importa konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

1. Atlasiet **Bagātināt manus datus** SFTP pielāgotās **importēšanas** elementā.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP pielāgotā importa rūts.":::

1. Pārskatiet pārskatu un pēc tam atlasiet **Tālāk**.

1. Atlasiet savienojumu. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. **Atlasiet klienta datu kopu** un izvēlieties profilu vai segmentu, kuru vēlaties bagātināt. Klienta *entītija* bagātina visus jūsu klientu profilus, savukārt segments bagātina tikai šajā segmentā ietvertos klientu profilus.

1. Atlasiet **Tālāk**.

1. **Ievadiet tā datu faila ceļu** un **faila nosaukumu**, kuru vēlaties importēt.

1. Atlasiet **Tālāk**.

1. **Norādiet bagātināšanas nosaukumu** un izvades entītijas **nosaukumu**.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**.

1. Atlasiet **Palaist**, lai sāktu bagātināšanas procesu, vai aizveriet, lai **atgrieztos bagātināšanas** lapā.

## <a name="view-enrichment-results"></a>Bagātināšanas rezultātu skatīšana

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
