---
title: Bagātināšana ar SFTP pielāgoto importu
description: Vispārīga informācija par SFTP pielāgoto importēšanu.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 657afb6fcb68429680eb677734b4115e69769008
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953728"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Bagātiniet klientu profilus ar pielāgotiem datiem (priekšskatījums)

Faila drošas pārsūtīšanas protokola (SFTP) pielāgotā importēšana ļauj importēt datus, kuriem nav jāiziet datu apvienošanas process. Tas ir elastīgs, drošs un viegls veids, kā apkopot datus. SFTP pielāgoto importēšanu var izmantot savienojumā ar [SFTP Export](export-sftp.md), kas ļauj eksportēt bagātināšanai nepieciešamos klientu profilu datus. Pēc tam datus var apstrādāt un bagātināt, un SFTP pielāgoto importēšanu var izmantot, lai bagātinātos datus atgrieztu Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Priekšnoteikumi

- Ir zināms SFTP resursdatorā importējamā faila nosaukums un atrašanās vieta (ceļš).

- Ir *pieejams fails model.json*, kas norāda importējamo datu kopējā datu modeļa shēmu. Šim failam ir jābūt tajā pašā direktorijā, kur Importējamais fails.

- SFTP [savienojums](connections.md) ir [konfigurēts](#configure-the-connection-for-sftp-custom-import).

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

Jums jābūt Customer Insights administratoram [un](permissions.md#admin) jābūt tās SFTP atrašanās vietas lietotāja akreditācijas datiem, URL un porta numuram, no kuras vēlaties importēt datus.

1. **Atlasiet Pievienot savienojumu**, konfigurējot bagātināšanu, vai dodieties uz **Administrēšanas** > **savienojumiem** un atlasiet **Iestatīt** elementā Pielāgota importēšana.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Pielāgotas importēšanas savienojuma konfigurācijas lapa.":::

1. Ievadiet savienojuma nosaukumu.

1. Ievadiet derīgu lietotājvārdu, paroli un resursdatora URL SFTP serverim, kurā atrodas importējamie dati.

1. Pārskatiet un sniedziet savu piekrišanu [Datu konfidencialitātei un atbilstībai](#data-privacy-and-compliance), atlasot **Es piekrītu**.

1. Atlasiet **Pārbaudīt**, lai validētu konfigurāciju, un pēc tam atlasiet **Saglabāt**.

### <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Kad iespējojat Dynamics 365 Customer Insights pārsūtīt datus, izmantojot pielāgotu importēšanu, jūs atļaujat pārsūtīt datus ārpus atbilstības robežas, tostarp potenciāli sensitīviem Dynamics 365 Customer Insights datiem, piemēram, Personas datiem. Microsoft pārsūtīs šādus datus pēc jūsu norādījumiem, bet jūs esat atbildīgs par to, lai dati atbilstu visiem jūsu konfidencialitātes vai drošības pienākumiem. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu šīs funkcijas izmantošanu.

## <a name="configure-the-import"></a>Importa konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

1. Sftp pielāgotajā importēšanas **elementā atlasiet** Bagātināt manus **datus**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP pielāgotā importa rūts.":::

1. Pārskatiet pārskatu un pēc tam atlasiet **Tālāk**.

1. Atlasiet savienojumu. Ja tāds nav pieejams, sazinieties ar administratoru.

1. Atlasiet klienta datu kopu **un** izvēlieties profilu vai segmentu, kuru vēlaties bagātināt. Klientu *uzņēmums* bagātina visus jūsu klientu profilus, savukārt segments bagātina tikai šajā segmentā esošos klientu profilus.

1. Atlasiet **Tālāk**.

1. Ievadiet importējamā **datu faila ceļu** un **faila nosaukumu**.

1. Atlasiet **Tālāk**.

1. **Norādiet bagātināšanas nosaukumu** un entītijas **Izvade nosaukumu**.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**.

1. Atlasiet **Palaist**, lai sāktu bagātināšanas procesu, vai tuvu, lai **atgrieztos lapā Bagātinājumi**.

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
