---
title: Customer Insights datu eksportēšana uz Sendinblue
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314643"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="14e54-103">Segmentu eksportēšana uz Sendinblue (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="14e54-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="14e54-104">Eksportējiet vienotos klienta profila segmentus, lai ģenerētu kampaņas, nodrošinātu e-pasta mārketingu un izmantotu specifiskas klientu grupas pakalpojumā Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="14e54-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="14e54-105">Savienojuma priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="14e54-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="14e54-106">Jums ir [Sendinblue konts](https://www.sendinblue.com/) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="14e54-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="14e54-107">Sendinblue un atbilstošajos ID ir iekļauti jau esošie saraksti.</span><span class="sxs-lookup"><span data-stu-id="14e54-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="14e54-108">Jums ir [konfigurēti segmenti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="14e54-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="14e54-109">Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="14e54-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="14e54-110">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="14e54-110">Known limitations</span></span>

- <span data-ttu-id="14e54-111">Vienā eksportēšanas reizē uz Sendinblue var eksportēt līdz 1 miljonam profilu.</span><span class="sxs-lookup"><span data-stu-id="14e54-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="14e54-112">Eksportēšana uz Sendinblue attiecas tikai uz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="14e54-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="14e54-113">Segmentu eksportēšana, kur kopējais profilu skaits ir 1 miljons, var ilgt līdz 90 minūtēm.</span><span class="sxs-lookup"><span data-stu-id="14e54-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="14e54-114">Profilu skaits, ko var eksportēt uz Sendinblue ir atkarīgs un to ierobežo jūsu līgums ar Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="14e54-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="14e54-115">Savienojuma ar Sendinblue iestatīšana</span><span class="sxs-lookup"><span data-stu-id="14e54-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="14e54-116">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="14e54-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="14e54-117">Atlasiet vienumu **Pievienot savienojumu** un izvēlieties **Sendinblue**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="14e54-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="14e54-118">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="14e54-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="14e54-119">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="14e54-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="14e54-120">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="14e54-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="14e54-121">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="14e54-121">Choose who can use this connection.</span></span> <span data-ttu-id="14e54-122">Pēc noklusējuma ir tikai administratori.</span><span class="sxs-lookup"><span data-stu-id="14e54-122">By default it's only administrators.</span></span> <span data-ttu-id="14e54-123">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="14e54-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="14e54-124">Ievadiet savu **[Sendinblue API atslēgu](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="14e54-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="14e54-125">Atlasiet **Es piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību** un atlasiet **Savienot**, lai inicializētu savienojumu ar Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="14e54-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="14e54-126">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="14e54-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="14e54-127">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="14e54-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="14e54-128">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="14e54-128">Configure an export</span></span>

<span data-ttu-id="14e54-129">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="14e54-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="14e54-130">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="14e54-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="14e54-131">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="14e54-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="14e54-132">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="14e54-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="14e54-133">Laukam **Savienojums eksportēšanai** izvēlieties savienojumu no Sendinblue sadaļas.</span><span class="sxs-lookup"><span data-stu-id="14e54-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="14e54-134">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="14e54-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="14e54-135">Ievadiet savu **Sendinblue saraksta ID**</span><span class="sxs-lookup"><span data-stu-id="14e54-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="14e54-136">Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="14e54-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="14e54-137">Pēc izvēles, varat eksportēt **vārdu**, **uzvārdu** un **tālruņa numuru**, lai izveidotu personalizētākus e-pasta ziņojumus.</span><span class="sxs-lookup"><span data-stu-id="14e54-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="14e54-138">Atlasiet **Pievienot atribūtu**, lai kartētu šos laukus.</span><span class="sxs-lookup"><span data-stu-id="14e54-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="14e54-139">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="14e54-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="14e54-140">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="14e54-140">Select **Save**.</span></span>

<span data-ttu-id="14e54-141">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="14e54-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="14e54-142">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="14e54-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="14e54-143">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="14e54-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="14e54-144">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="14e54-144">Data privacy and compliance</span></span>

<span data-ttu-id="14e54-145">Iespējojot Dynamics 365 Customer Insights datu pārsūtīšanai uz Sendinblue, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežas, kas paredzēta Dynamics 365 Customer Insights, ieskaitot potenciāli sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="14e54-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="14e54-146">Microsoft šos datus pārsūtīs pēc jūsu norādījuma, bet jūs esat atbildīgs par to, lai Sendinblue atbilstu visām jūsu konfidencialitātes vai drošības saistībām.</span><span class="sxs-lookup"><span data-stu-id="14e54-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="14e54-147">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="14e54-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="14e54-148">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="14e54-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
