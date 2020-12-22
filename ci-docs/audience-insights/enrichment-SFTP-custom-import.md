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
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="3e2dc-103">Bagātiniet klientu profilus ar pielāgotiem datiem (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="3e2dc-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="3e2dc-104">Faila drošas pārsūtīšanas protokola (SFTP) pielāgotā importēšana ļauj importēt datus, kuriem nav jāiziet datu apvienošanas process.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="3e2dc-105">Tas ir elastīgs, drošs un viegls veids, kā apkopot datus.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="3e2dc-106">SFTP pielāgoto importēšanu var izmantot savienojumā ar [SFTP Export](export-sftp.md), kas ļauj eksportēt bagātināšanai nepieciešamos klientu profilu datus.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="3e2dc-107">Šos datus var apstrādāt, bagātināt, un SFTP pielāgoto importēšanu var izmantot, lai atgrieztu bagātinātos datus atpakaļ auditorijas ieskatu iespējā Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3e2dc-108">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="3e2dc-108">Prerequisites</span></span>

<span data-ttu-id="3e2dc-109">Lai konfigurētu SFTP pielāgoto importēšanu, ir jāatbilst šādiem priekšnosacījumiem:</span><span class="sxs-lookup"><span data-stu-id="3e2dc-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="3e2dc-110">Jums ir lietotāja akreditācijas dati (lietotājvārds un parole) attiecībā uz SFTP atrašanās vietu, kur tiek iegūti no programmas importējamie dati.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="3e2dc-111">Jums ir vietrādis URL un porta numurs (parasti 22) STFP resursdatoram.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="3e2dc-112">Jums ir faila nosaukums un atrašanās vieta importējamā faila SFTP resursdatorā.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="3e2dc-113">Ir *model.json* fails, kas norāda importējamo datu shēmu.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="3e2dc-114">Šim failam ir jābūt tajā pašā direktorijā, kur Importējamais fails.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="3e2dc-115">ir nepieciešamas [Administratora](permissions.md#administrator) atļaujas.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="3e2dc-116">Konfigurācija</span><span class="sxs-lookup"><span data-stu-id="3e2dc-116">Configuration</span></span>

1. <span data-ttu-id="3e2dc-117">dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="3e2dc-118">Elementā **SFTP pielāgotā importēšana** atlasiet **Bagātināt manus datus**.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3e2dc-119">![Elements SFTP pielāgotā importēšana](media/SFTP_Custom_Import_tile.png "Elements SFTP pielāgotā importēšana")</span><span class="sxs-lookup"><span data-stu-id="3e2dc-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="3e2dc-120">Atlasiet **Sākt darbu** un sniedziet akreditācijas datu un adresi, kas paredzēta SFTP serverim.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="3e2dc-121">Piemēram, sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="3e2dc-122">Ievadiet tā faila nosaukumu, kurā ir ietverti dati, un ceļu uz failu SFTP serverī, ja tas nav iekļauts saknes mapē.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="3e2dc-123">Apstipriniet visas ievades, atlasot **Izveidot savienojumu ar pielāgoto importēšanu**.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3e2dc-124">![SFTP pielāgotās importēšanas izlidošana](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP pielāgotās importēšanas izlidošana")</span><span class="sxs-lookup"><span data-stu-id="3e2dc-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="3e2dc-125">Notiek lauku kartējumu ģenerēšana</span><span class="sxs-lookup"><span data-stu-id="3e2dc-125">Defining field mappings</span></span> 

<span data-ttu-id="3e2dc-126">Direktorijā, kurā ir fails, kas tiks importēts uz SFTP servera, ir jābūt iekļautam arī *model.json* failam.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="3e2dc-127">Šis fails definē datu importēšanai izmantojamo shēmu.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="3e2dc-128">Shēmai ir jāizmanto [Common Data Model](https://docs.microsoft.com/common-data-model/), lai norādītu lauka kartējumu.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="3e2dc-129">Vienkāršs model.json faila piemērs izskatās šādi:</span><span class="sxs-lookup"><span data-stu-id="3e2dc-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="3e2dc-130">Bagātināšanas rezultāti</span><span class="sxs-lookup"><span data-stu-id="3e2dc-130">Enrichment results</span></span>

<span data-ttu-id="3e2dc-131">Lai sāktu bagātināšanas procesu, komandjoslā atlasiet **Palaist**.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="3e2dc-132">Varat arī ļaut sistēmai palaist bagātināšanu automātiski kā daļu no [plānotās atsvaidzināšanas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3e2dc-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3e2dc-133">Apstrādes laiks būs atkarīgs no importējamo datu apjoma un savienojuma ar SFTP serveri.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="3e2dc-134">Pēc bagātināšanas procesa pabeigšanas varat pārskatīt jūsu tikko importētos pielāgotos datus par bagātināšanu zem **Manas bagātināšanas**.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="3e2dc-135">Turklāt jūs redzēsit pēdējā atjauninājuma laiku un bagātināto profilu skaitu.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="3e2dc-136">Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3e2dc-137">Nākamās darbības</span><span class="sxs-lookup"><span data-stu-id="3e2dc-137">Next steps</span></span>

<span data-ttu-id="3e2dc-138">Būvējiet virs saviem bagātinātajiem klientu datiem.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="3e2dc-139">Veidojiet [segmentus](segments.md), [mērus](measures.md) un pat [eksportējiet datus](export-destinations.md), lai sniegtu klientiem personalizētas iespējas.</span><span class="sxs-lookup"><span data-stu-id="3e2dc-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


