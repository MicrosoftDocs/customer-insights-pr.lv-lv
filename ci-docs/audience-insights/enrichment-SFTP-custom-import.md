---
title: Bagātināšana ar SFTP pielāgoto importu
description: Vispārīga informācija par SFTP pielāgoto importēšanu.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896290"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="e6448-103">Bagātiniet klientu profilus ar pielāgotiem datiem (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="e6448-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="e6448-104">Drošas failu pārsūtīšanas protokola (SFTP) pielāgotais imports ļauj importēt datus, kuriem nav jāiziet datu apvienošanas process.</span><span class="sxs-lookup"><span data-stu-id="e6448-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that does not have to go through the process of data unification.</span></span> <span data-ttu-id="e6448-105">Tas ir elastīgs, drošs un viegls veids, kā apkopot datus.</span><span class="sxs-lookup"><span data-stu-id="e6448-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="e6448-106">SFTP pielāgoto importēšanu var izmantot savienojumā ar [SFTP Export](export-sftp.md), kas ļauj eksportēt bagātināšanai nepieciešamos klientu profilu datus.</span><span class="sxs-lookup"><span data-stu-id="e6448-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="e6448-107">Šos datus var apstrādāt, bagātināt, un SFTP pielāgoto importēšanu var izmantot, lai atgrieztu bagātinātos datus atpakaļ auditorijas ieskatu iespējā Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e6448-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e6448-108">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="e6448-108">Prerequisites</span></span>

<span data-ttu-id="e6448-109">Lai konfigurētu SFTP pielāgoto importēšanu, ir jāatbilst šādiem priekšnosacījumiem:</span><span class="sxs-lookup"><span data-stu-id="e6448-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="e6448-110">Jums ir STFP hostā importējamā faila nosaukums un atrašanās vieta (ceļš).</span><span class="sxs-lookup"><span data-stu-id="e6448-110">You have the filename and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="e6448-111">Ir *model.json* fails, kurā norādīta importējamo datu [Common Data Model shēma](/common-data-model/).</span><span class="sxs-lookup"><span data-stu-id="e6448-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="e6448-112">Šim failam ir jābūt tajā pašā direktorijā, kur Importējamais fails.</span><span class="sxs-lookup"><span data-stu-id="e6448-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="e6448-113">Administrators jau ir konfigurējis SFTP savienojumu *vai* jums ir [administratora](permissions.md#administrator) atļaujas.</span><span class="sxs-lookup"><span data-stu-id="e6448-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="e6448-114">Jums būs nepieciešami lietotāja akreditācijas dati un STFP atrašanās vietas, no kuras vēlaties importēt datus, URL un porta numurs.</span><span class="sxs-lookup"><span data-stu-id="e6448-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="e6448-115">Importa konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="e6448-115">Configure the import</span></span>

1. <span data-ttu-id="e6448-116">dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.</span><span class="sxs-lookup"><span data-stu-id="e6448-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="e6448-117">**SFTP pielāgotās importēšanas rūtī** atlasiet **Bagātināt manus datus** un pēc tam atlasiet **Sākt darbu**.</span><span class="sxs-lookup"><span data-stu-id="e6448-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP pielāgotā importa rūts.":::

1. <span data-ttu-id="e6448-119">Nolaižamajā izvēlnē atlasiet [savienojums](connections.md).</span><span class="sxs-lookup"><span data-stu-id="e6448-119">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="e6448-120">Ja nav pieejamu savienojumu, sazinieties ar administratoru.</span><span class="sxs-lookup"><span data-stu-id="e6448-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="e6448-121">Ja esat administrators, jūs varat izveidot savienojumu, atlasot **Pievienot savienojumu** un nolaižamajā izvēlnē izvēloties **SFTP pielāgotais imports**.</span><span class="sxs-lookup"><span data-stu-id="e6448-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the drop-down.</span></span>

1. <span data-ttu-id="e6448-122">Atlasiet **Pieslēgties Custom Import**, lai apstiprinātu atlasīto savienojumu.</span><span class="sxs-lookup"><span data-stu-id="e6448-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="e6448-123">Atlasiet **Tālāk** un ievadiet datu faila, kuru vēlaties importēt, **Nosaukumu** un **Ceļu**.</span><span class="sxs-lookup"><span data-stu-id="e6448-123">Select **Next** and enter the **Filename** and **Path** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Ekrānuzņēmums, ievadot datu atrašanās vietu.":::

1. <span data-ttu-id="e6448-125">Atlasiet **Tālāk** un norādiet bagātināmo datu nosaukumu un izvades entitījas nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="e6448-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="e6448-126">Pēc izvēļu pārskatīšanas atlasiet **Saglabāt vidi**.</span><span class="sxs-lookup"><span data-stu-id="e6448-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="e6448-127">SFTP Custom Import savienojuma konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="e6448-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="e6448-128">Lai konfigurētu savienojumus, jums ir jābūt administratoram.</span><span class="sxs-lookup"><span data-stu-id="e6448-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="e6448-129">Konfigurējot bagātinātos datus, atlasiet **Pievienot savienojumu** *vai* dodieties uz **Administrators** > **Savienojumi** un Custom Import rūtī atlasiet **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="e6448-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="e6448-130">Lodziņā **Parādāmais nosaukums** ievadiet savienojuma nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="e6448-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="e6448-131">Ievadiet derīgu lietotājvārdu un paroli un hosta URL STFP serverim, kurā atrodas importējamie dati.</span><span class="sxs-lookup"><span data-stu-id="e6448-131">Enter valid user name, password, and host URL for the STFP server the data to be imported resides on.</span></span>

1. <span data-ttu-id="e6448-132">Pārskatiet un sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atzīmējot izvēles rūtiņu **Piekrītu**.</span><span class="sxs-lookup"><span data-stu-id="e6448-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="e6448-133">Lai pārbaudītu konfigurāciju, atlasiet **Pārbaudīt**.</span><span class="sxs-lookup"><span data-stu-id="e6448-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="e6448-134">Kolīdz pārbaude ir pabeigta, savienojumu var saglabāt, noklikšķinot uz **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="e6448-134">Once the verification has completed, the connection can be saved by clicking **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="e6448-135">![Experian savienojuma konfigurācijas lapa](media/enrichment-SFTP-connection.png "Experian savienojuma konfigurācijas lapa.")</span><span class="sxs-lookup"><span data-stu-id="e6448-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="e6448-136">Notiek lauku kartējumu ģenerēšana</span><span class="sxs-lookup"><span data-stu-id="e6448-136">Defining field mappings</span></span> 

<span data-ttu-id="e6448-137">Direktorijā, kurā ir fails, kas tiks importēts uz SFTP servera, ir jābūt iekļautam arī *model.json* failam.</span><span class="sxs-lookup"><span data-stu-id="e6448-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="e6448-138">Šis fails definē datu importēšanai izmantojamo shēmu.</span><span class="sxs-lookup"><span data-stu-id="e6448-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="e6448-139">Shēmai ir jāizmanto [Common Data Model](/common-data-model/), lai norādītu lauka kartējumu.</span><span class="sxs-lookup"><span data-stu-id="e6448-139">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="e6448-140">Vienkāršs model.json faila piemērs izskatās šādi:</span><span class="sxs-lookup"><span data-stu-id="e6448-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="e6448-141">Bagātināšanas rezultāti</span><span class="sxs-lookup"><span data-stu-id="e6448-141">Enrichment results</span></span>

<span data-ttu-id="e6448-142">Lai sāktu bagātināšanas procesu, komandjoslā atlasiet **Palaist**.</span><span class="sxs-lookup"><span data-stu-id="e6448-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="e6448-143">Varat arī ļaut sistēmai palaist bagātināšanu automātiski kā daļu no [plānotās atsvaidzināšanas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e6448-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e6448-144">Apstrādes laiks būs atkarīgs no importējamo datu apjoma un savienojuma ar SFTP serveri.</span><span class="sxs-lookup"><span data-stu-id="e6448-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="e6448-145">Pēc bagātināšanas procesa pabeigšanas varat pārskatīt jūsu tikko importētos pielāgotos datus par bagātināšanu zem **Manas bagātināšanas**.</span><span class="sxs-lookup"><span data-stu-id="e6448-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="e6448-146">Turklāt jūs redzēsit pēdējā atjauninājuma laiku un bagātināto profilu skaitu.</span><span class="sxs-lookup"><span data-stu-id="e6448-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="e6448-147">Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.</span><span class="sxs-lookup"><span data-stu-id="e6448-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e6448-148">Nākamās darbības</span><span class="sxs-lookup"><span data-stu-id="e6448-148">Next steps</span></span>

<span data-ttu-id="e6448-149">Būvējiet virs saviem bagātinātajiem klientu datiem.</span><span class="sxs-lookup"><span data-stu-id="e6448-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e6448-150">Veidojiet [segmentus](segments.md), [mērus](measures.md) un pat [eksportējiet datus](export-destinations.md), lai sniegtu klientiem personalizētas iespējas.</span><span class="sxs-lookup"><span data-stu-id="e6448-150">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
