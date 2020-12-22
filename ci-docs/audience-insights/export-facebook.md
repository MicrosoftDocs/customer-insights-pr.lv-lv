---
title: Customer Insights datu eksportēšana uz Facebook Ads Manager
description: Uzziniet, kā konfigurēt savienojumu ar Facebook Ads Manager.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643692"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="1cf5b-103">Facebook Ads Manager savienotājs (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="1cf5b-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="1cf5b-104">Eksportējiet vienotu klientu profilu segmentus uz Facebook Ads Manager, lai izveidotu kampaņas platformās Facebook un Instagram.</span><span class="sxs-lookup"><span data-stu-id="1cf5b-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1cf5b-105">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="1cf5b-105">Prerequisites</span></span>

- <span data-ttu-id="1cf5b-106">Jums ir nepieciešams [**Facebook Reklāmu konts**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), kas ietver [**Facebook Biznesa kontu**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="1cf5b-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="1cf5b-107">Jums ir jābūt [**Facebook Reklāmu konta**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) administratoram.</span><span class="sxs-lookup"><span data-stu-id="1cf5b-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="1cf5b-108">Savienojuma izveide ar Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="1cf5b-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="1cf5b-109">Dodieties uz sadaļu **Administrators** > **Eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="1cf5b-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1cf5b-110">Sadaļā **Facebook Ads Manager** atlasiet **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="1cf5b-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="1cf5b-111">Piešķiriet eksportēšanas galamērķim atpazīstamu nosaukumu laukā **Parādāmais nosaukums**.</span><span class="sxs-lookup"><span data-stu-id="1cf5b-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="1cf5b-112">Atlasiet **Turpināt ar Facebook**, lai pierakstītos savā Facebook Reklāmu kontā.</span><span class="sxs-lookup"><span data-stu-id="1cf5b-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="1cf5b-113">Atļaut **ads_management** atļauju pēc autentificēšanās Facebook.</span><span class="sxs-lookup"><span data-stu-id="1cf5b-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="1cf5b-114">Atlasiet **Facebook Reklāmu kontu**, ar kuru vēlaties strādāt.</span><span class="sxs-lookup"><span data-stu-id="1cf5b-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="1cf5b-115">Nolaižamajā sarakstā atlasiet **Esošā pielāgotā auditorija** vai izveidojiet **Jaunu pielāgotu auditoriju**.</span><span class="sxs-lookup"><span data-stu-id="1cf5b-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="1cf5b-116">Papildinformāciju skatiet rakstā [**Auditorijas Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="1cf5b-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="1cf5b-117">Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="1cf5b-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1cf5b-118">Lai konfigurētu eksportēšanu, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="1cf5b-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="1cf5b-119">Savienotāja konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="1cf5b-119">Configure the connector</span></span>

1. <span data-ttu-id="1cf5b-120">Lodziņā **Izvēlieties atslēgas identifikatora lauku** atlasiet **E-pasts**, **Vārds, uzvārds un adrese** vai **Tālrunis**, ko nosūtīt Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="1cf5b-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="1cf5b-121">Kartējiet atbilstošos atribūtus no savas vienotās klienta entītijas atlasītajam galvenajam identifikatoram.</span><span class="sxs-lookup"><span data-stu-id="1cf5b-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="1cf5b-122">[PADOMS] Labākās atbilstības iespējas parādās, ja kā galveno identifikatoru atlasāt **E-pastu**.</span><span class="sxs-lookup"><span data-stu-id="1cf5b-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="1cf5b-123">Atbilstība var uzlaboties, pievienojot papildu identifikatorus.</span><span class="sxs-lookup"><span data-stu-id="1cf5b-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="1cf5b-124">Atlasiet **Pievienot atribūtu**, lai kartētu papildu atribūtus, kurus nosūtīt Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="1cf5b-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="1cf5b-125">Atribūti no Facebook Reklāmu pārvaldnieka tiek kartēti uz šādiem lietotājam draudzīgiem nosaukumiem: **FN** = **Vārds**, **LN** = **Uzvārds**, **FI** = **Pirmais iniciālis**, **PHONE** = **Tālrunis**, **GEN** = **Dzimums**, **DOB** = **Dzimšanas datums**, **ST** = **Štats**, **CT** = **Pilsēta**, **ZIP** = **Pasta indekss / ZIP kods**, **COUNTRY** = **Valsts/reģions**</span><span class="sxs-lookup"><span data-stu-id="1cf5b-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="1cf5b-126">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="1cf5b-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="1cf5b-127">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="1cf5b-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="1cf5b-128">Datu eksportēšana</span><span class="sxs-lookup"><span data-stu-id="1cf5b-128">Export the data</span></span>

<span data-ttu-id="1cf5b-129">Datus var [eksportēt pēc pieprasījuma](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="1cf5b-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="1cf5b-130">Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1cf5b-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1cf5b-131">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="1cf5b-131">Data privacy and compliance</span></span>

<span data-ttu-id="1cf5b-132">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanai uz Facebook Ads Manager, jūs atļaujat datu pārsūtīšanu ārpus Dynamics 365 Customer Insights atbilstības robežām, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="1cf5b-132">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1cf5b-133">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Facebook Ads atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="1cf5b-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="1cf5b-134">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1cf5b-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1cf5b-135">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="1cf5b-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
