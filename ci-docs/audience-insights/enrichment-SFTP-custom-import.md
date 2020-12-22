---
title: Bagātināšana ar SFTP pielāgoto importu
description: Vispārīga informācija par SFTP pielāgoto importēšanu.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 59f7f05ca0825ba147e9e93f10fa3508ec3a16dd
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568471"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Bagātiniet klientu profilus ar pielāgotiem datiem (priekšskatījums)

Faila drošas pārsūtīšanas protokola (SFTP) pielāgotā importēšana ļauj importēt datus, kuriem nav jāiziet datu apvienošanas process. Tas ir elastīgs, drošs un viegls veids, kā apkopot datus. SFTP pielāgoto importēšanu var izmantot savienojumā ar [SFTP Export](export-sftp.md), kas ļauj eksportēt bagātināšanai nepieciešamos klientu profilu datus. Šos datus var apstrādāt, bagātināt, un SFTP pielāgoto importēšanu var izmantot, lai atgrieztu bagātinātos datus atpakaļ auditorijas ieskatu iespējā Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Priekšnosacījumi

Lai konfigurētu SFTP pielāgoto importēšanu, ir jāatbilst šādiem priekšnosacījumiem:

- Jums ir lietotāja akreditācijas dati (lietotājvārds un parole) attiecībā uz SFTP atrašanās vietu, kur tiek iegūti no programmas importējamie dati.
- Jums ir vietrādis URL un porta numurs (parasti 22) STFP resursdatoram.
- Jums ir faila nosaukums un atrašanās vieta importējamā faila SFTP resursdatorā.
- Ir *model.json* fails, kas norāda importējamo datu shēmu. Šim failam ir jābūt tajā pašā direktorijā, kur Importējamais fails.
- ir nepieciešamas [Administratora](permissions.md#administrator) atļaujas.

## <a name="configuration"></a>Konfigurācija

1. dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

1. Elementā **SFTP pielāgotā importēšana** atlasiet **Bagātināt manus datus**.

   > [!div class="mx-imgBorder"]
   > ![Elements SFTP pielāgotā importēšana](media/SFTP_Custom_Import_tile.png "Elements SFTP pielāgotā importēšana")

1. Atlasiet **Sākt darbu** un sniedziet akreditācijas datu un adresi, kas paredzēta SFTP serverim. Piemēram, sftp://mysftpserver.com:22.

1. Ievadiet tā faila nosaukumu, kurā ir ietverti dati, un ceļu uz failu SFTP serverī, ja tas nav iekļauts saknes mapē.

1. Apstipriniet visas ievades, atlasot **Izveidot savienojumu ar pielāgoto importēšanu**.

   > [!div class="mx-imgBorder"]
   > ![SFTP pielāgotās importēšanas izlidošana](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP pielāgotās importēšanas izlidošana")

## <a name="defining-field-mappings"></a>Notiek lauku kartējumu ģenerēšana 

Direktorijā, kurā ir fails, kas tiks importēts uz SFTP servera, ir jābūt iekļautam arī *model.json* failam. Šis fails definē datu importēšanai izmantojamo shēmu. Shēmai ir jāizmanto [Common Data Model](https://docs.microsoft.com/common-data-model/), lai norādītu lauka kartējumu. Vienkāršs model.json faila piemērs izskatās šādi:

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

Būvējiet virs saviem bagātinātajiem klientu datiem. Veidojiet [segmentus](segments.md), [mērus](measures.md) un pat [eksportējiet datus](export-destinations.md), lai sniegtu klientiem personalizētas iespējas.


