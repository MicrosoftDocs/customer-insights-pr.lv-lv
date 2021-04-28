---
title: Customer Insights datu eksportēšana uz Facebook Ads Manager
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca32906a98bc734639fb369d6f5a92e8888fd850
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906819"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="9893c-103">Segmentu saraksta eksportēšana uz Facebook Ads Manager (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="9893c-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="9893c-104">Eksportējiet vienotu klientu profilu segmentus uz Facebook Ads Manager, lai izveidotu kampaņas platformās Facebook un Instagram.</span><span class="sxs-lookup"><span data-stu-id="9893c-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="9893c-105">Savienojuma priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="9893c-105">Prerequisites for connection</span></span>

- <span data-ttu-id="9893c-106">Ir jābūt [**Facebook Ad kontam**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), kas ietver [**Facebook Business kontu**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="9893c-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="9893c-107">Jums ir jābūt [**Facebook Reklāmu konta**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) administratoram.</span><span class="sxs-lookup"><span data-stu-id="9893c-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9893c-108">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="9893c-108">Known limitations</span></span>

- <span data-ttu-id="9893c-109">Līdz 10 miljoniem klientu profilu eksportēšanai uz Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="9893c-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="9893c-110">Eksportēšana uz Facebook Ads Manager ir atļauta tikai segmentiem.</span><span class="sxs-lookup"><span data-stu-id="9893c-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="9893c-111">Izveidojiet vai atjauniniet pielāgoto auditoriju Facebook no veida tikai *klientu saraksts*.</span><span class="sxs-lookup"><span data-stu-id="9893c-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="9893c-112">Eksportējot segmentus kopā ar 10 000 000 profiliem, var būt nepieciešamas 90 minūtes.</span><span class="sxs-lookup"><span data-stu-id="9893c-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="9893c-113">Savienojuma ar Facebook Ads Manager izveidošana</span><span class="sxs-lookup"><span data-stu-id="9893c-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="9893c-114">Iekams lietotāji var izveidot eksportu, administratoram ir jākonfigurē savienojums ar pakalpojumu un jāļauj līdzstrādniekiem izmantot savienojumu.</span><span class="sxs-lookup"><span data-stu-id="9893c-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="9893c-115">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="9893c-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9893c-116">Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Facebook Ads Manager**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="9893c-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="9893c-117">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="9893c-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9893c-118">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="9893c-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9893c-119">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="9893c-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9893c-120">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="9893c-120">Choose who can use this connection.</span></span> <span data-ttu-id="9893c-121">Ja nesāksit nekādas darbības, noklusējums būs **Administratori**.</span><span class="sxs-lookup"><span data-stu-id="9893c-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="9893c-122">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9893c-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="9893c-123">Autentificējieties, izmantojot Facebook Ads:</span><span class="sxs-lookup"><span data-stu-id="9893c-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="9893c-124">Atlasiet **Turpināt ar Facebook**, lai pierakstītos savā Facebook Reklāmu kontā.</span><span class="sxs-lookup"><span data-stu-id="9893c-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="9893c-125">Atļaut **ads_management** atļauju pēc autentificēšanās Facebook.</span><span class="sxs-lookup"><span data-stu-id="9893c-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="9893c-126">Atlasiet **Facebook Reklāmu kontu**, ar kuru vēlaties strādāt.</span><span class="sxs-lookup"><span data-stu-id="9893c-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="9893c-127">Nolaižamajā sarakstā atlasiet **Esošā pielāgotā auditorija** vai izveidojiet **Jaunu pielāgotu auditoriju**.</span><span class="sxs-lookup"><span data-stu-id="9893c-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="9893c-128">Papildinformāciju skatiet rakstā [**Auditorijas Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="9893c-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="9893c-129">Šajā eksportā jūs varat Facebook izveidot vai atjaunināt pielāgotās auditorijas vienīgi ar veidu *klientu saraksts*.</span><span class="sxs-lookup"><span data-stu-id="9893c-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="9893c-130">Dažos gadījumos nolaižamajā sarakstā ir redzamas dažādu veidu pielāgotās auditorijas.</span><span class="sxs-lookup"><span data-stu-id="9893c-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="9893c-131">Ja atlasīsiet auditoriju, kuras veids nav *klientu saraksts*, eksportēšana neizdosies.</span><span class="sxs-lookup"><span data-stu-id="9893c-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="9893c-132">Pārskatiet lapu **Datu privātums un atbilstība** un atlasiet **Es piekrītu**.</span><span class="sxs-lookup"><span data-stu-id="9893c-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="9893c-133">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="9893c-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="9893c-134">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="9893c-134">Configure an export</span></span>

<span data-ttu-id="9893c-135">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="9893c-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9893c-136">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9893c-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9893c-137">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="9893c-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9893c-138">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="9893c-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="9893c-139">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas **Facebook Ads Manager**</span><span class="sxs-lookup"><span data-stu-id="9893c-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="9893c-140">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="9893c-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="9893c-141">Lodziņā **Izvēlieties atslēgas identifikatora lauku** atlasiet **E-pasts**, **Vārds, uzvārds un adrese** vai **Tālrunis**, ko nosūtīt Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="9893c-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="9893c-142">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="9893c-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="9893c-143">Kartējiet atbilstošos atribūtus no savas vienotās klienta entītijas atlasītajam galvenajam identifikatoram.</span><span class="sxs-lookup"><span data-stu-id="9893c-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="9893c-144">[PADOMS] Labākās atbilstības iespējas parādās, ja kā galveno identifikatoru atlasāt **E-pastu**.</span><span class="sxs-lookup"><span data-stu-id="9893c-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="9893c-145">Atbilstība var uzlaboties, pievienojot papildu identifikatorus.</span><span class="sxs-lookup"><span data-stu-id="9893c-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="9893c-146">Atlasiet **Pievienot atribūtu**, lai kartētu vairāk atribūtu, ko nosūtīt uz Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="9893c-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="9893c-147">xAtribūti no Facebook Reklāmu pārvaldnieka tiek kartēti uz šādiem lietotājam draudzīgiem nosaukumiem: **FN** = **Vārds**, **LN** = **Uzvārds**, **FI** = **Pirmais iniciālis**, **PHONE** = **Tālrunis**, **GEN** = **Dzimums**, **DOB** = **Dzimšanas datums**, **ST** = **Štats**, **CT** = **Pilsēta**, **ZIP** = **Pasta indekss / ZIP kods**, **COUNTRY** = **Valsts/reģions**</span><span class="sxs-lookup"><span data-stu-id="9893c-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="9893c-148">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="9893c-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="9893c-149">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="9893c-149">Select **Save**.</span></span>

<span data-ttu-id="9893c-150">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="9893c-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9893c-151">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9893c-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9893c-152">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9893c-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9893c-153">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="9893c-153">Data privacy and compliance</span></span>

<span data-ttu-id="9893c-154">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanai uz Facebook Ads Manager, jūs atļaujat datu pārsūtīšanu ārpus Dynamics 365 Customer Insights atbilstības robežām, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="9893c-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9893c-155">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Facebook Ads atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="9893c-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="9893c-156">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9893c-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9893c-157">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="9893c-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
