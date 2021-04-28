---
title: Customer Insights datu eksportēšana uz Constant Contact
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a9372cc4ffa4fb112a96b1286aee9dc35059a50
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760581"
---
# <a name="export-segment-lists-to-constant-contact-preview"></a><span data-ttu-id="d9922-103">Segmentu sarakstu eksportēšana uz Constant Contact (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="d9922-103">Export segment lists to Constant Contact (preview)</span></span>

<span data-ttu-id="d9922-104">Eksportējiet vienoto klientu profilu segmentus uz Constant Contact un izmantojiet tos mārketinga darbībās.</span><span class="sxs-lookup"><span data-stu-id="d9922-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="d9922-105">Savienojuma priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="d9922-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="d9922-106">Jums ir [Constant Contact konts](https://www.constantcontact.com/account-home) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="d9922-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d9922-107">Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="d9922-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d9922-108">Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="d9922-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d9922-109">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="d9922-109">Known limitations</span></span>

- <span data-ttu-id="d9922-110">Jūs varat eksportēt līdz 1 miljonam profilu uz katru eksportu uz Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="d9922-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="d9922-111">Eksportēšana uz Constant Contact attiecas tikai uz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="d9922-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="d9922-112">Līdz 1 miljona profilu eksportēšana uz Constant Contact var aizņemt līdz 1 stundai.</span><span class="sxs-lookup"><span data-stu-id="d9922-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="d9922-113">Profilu, kurus varat eksportēt uz Constant Contact, skaits ir atkarīgs no jūsu līguma ar Constant Contract un attiecas vienīgi uz tā tvērumu.</span><span class="sxs-lookup"><span data-stu-id="d9922-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="d9922-114">Savienojuma ar Constant Contact izveide</span><span class="sxs-lookup"><span data-stu-id="d9922-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="d9922-115">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="d9922-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d9922-116">Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Constant Contact**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="d9922-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="d9922-117">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="d9922-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d9922-118">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="d9922-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d9922-119">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="d9922-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d9922-120">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="d9922-120">Choose who can use this connection.</span></span> <span data-ttu-id="d9922-121">Ja nesāksit nekādas darbības, noklusējums būs Administratori.</span><span class="sxs-lookup"><span data-stu-id="d9922-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d9922-122">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d9922-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d9922-123">Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="d9922-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d9922-124">Lai uzsāktu savienojumu ar Constant Contact, atlasiet **Savienot**.</span><span class="sxs-lookup"><span data-stu-id="d9922-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="d9922-125">Atlasiet **Autentificēt ar AdRoll** un norādiet savus Constant Contact administratora akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="d9922-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="d9922-126">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="d9922-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d9922-127">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="d9922-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d9922-128">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="d9922-128">Configure an export</span></span>

<span data-ttu-id="d9922-129">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="d9922-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d9922-130">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d9922-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d9922-131">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="d9922-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d9922-132">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="d9922-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d9922-133">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="d9922-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="d9922-134">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="d9922-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d9922-135">Ievadiet savu [**Constant Contact saraksta ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="d9922-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="d9922-136">Constant Contact atveriet sarakstu, lai URL vietrādī atrastu saraksta ID.</span><span class="sxs-lookup"><span data-stu-id="d9922-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="d9922-137">Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="d9922-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d9922-138">Segmenti ir obligāti jāeksportē uz Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="d9922-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="d9922-139">Ja vēlaties, varat eksportēt Vārds un Uzvārds kā papildu laukus, lai izveidotu vairāk personalizētu e-pasta ziņojumu.</span><span class="sxs-lookup"><span data-stu-id="d9922-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="d9922-140">Atlasiet **Pievienot atribūtu**, lai kartētu šos laukus.</span><span class="sxs-lookup"><span data-stu-id="d9922-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="d9922-141">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="d9922-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="d9922-142">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="d9922-142">Select **Save**.</span></span>

<span data-ttu-id="d9922-143">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="d9922-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d9922-144">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d9922-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d9922-145">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d9922-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d9922-146">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="d9922-146">Data privacy and compliance</span></span>

<span data-ttu-id="d9922-147">Iespējojot Dynamics 365 Customer Insights datu pārnesi uz Constant Contact, jūs ļaujat datus pārnest ārpus Dynamics 365 Customer Insights atbilstības robežām, ieskaitot potenciāli sensitīvus datus, tostarp, personas datus.</span><span class="sxs-lookup"><span data-stu-id="d9922-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d9922-148">Microsoft šos datus pārvirzīs atbilstoši jūsu norādījumiem, taču jūs atbildat par to, ka Constant Contact atbilst jebkādiem jūsu privātuma vai drošības nosacījumiem.</span><span class="sxs-lookup"><span data-stu-id="d9922-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d9922-149">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d9922-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d9922-150">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="d9922-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
