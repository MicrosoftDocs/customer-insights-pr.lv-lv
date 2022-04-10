---
title: Izveidot saiti starp auditorijas ieskatiem un iesaistes ieskatiem
description: Izveidot aktīvu saiti starp auditorijas ieskatiem un iesaistes ieskatiem, lai iespējotu datu abpusēju kopīgošanu.
ms.date: 09/08/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 56adc206d83bc6e34a55f11383393b5ac66da531
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229881"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Izveidot saiti starp auditorijas ieskatiem un iesaistes ieskatiem

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Integrācija starp iesaistes ieskatiem un auditorijas ieskatiem saista vidi no abām iespējām un nodrošina iespēju tos abpusēji koplietot.

Izmantojiet vienotos profilus un segmentus no auditorijas ieskatiem, lai iesaistes ieskatos izmantotu citas analīzes opcijas. Eksportējiet notikumus, kuriem ir augsta biznesa vērtība, izmantojot iesaistes ieskatus. Izmantojiet šos notikumus, lai vienotiem auditorijas ieskatu profiliem pievienotu datus.

## <a name="prerequisites"></a>Priekšnosacījumi

- Auditorijas ieskatu profili ir jāsaglabā jums piederošajā Azure Data Lake Storage kontā vai [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)&ndash;pārvaldītā datu ezerā. 
- Arī auditorijas ieskatu videi ir jābūt saistītai Dataverse videi. Un, ja šī vide datu krātuvei izmanto arī Dataverse, nodrošiniet, lai auditorijas ieskatos būtu pieejama opcija **Iespējot datu kopīgošanu**. Papildinformāciju skatiet sadaļā [Vides izveide un konfigurēšana auditorijas ieskatos](../audience-insights/create-environment.md).
- Administratora atļaujas ir nepieciešamas gan iesaistes ieskatu, gan auditorijas ieskatu vidē.
- Saistītajām vidēm ir jābūt vienā un tajā pašā ģeogrāfiskā reģionā.

> [!NOTE]
> - Ja jūsu auditorijas ieskatu abonements ir izmēģinājumversija, kurā tiek izmantoti auditorijas ieskati iekšēji pārvaldītajā Data Lake, sazinieties ar [pirequest@microsoft.com](mailto:pirequest@microsoft.com), lai saņemtu palīdzību. 
> - Ja jūsu auditorijas ieskatu vide izmanto Azure Data Lake Storage datu glabāšanai, jums krātuves kontam ir jāpievieno iesaistes ieskatu Azure pakalpojuma primāro nosaukumu jūsu krātuves kontam. Lai iegūtu detalizētu informāciju, skatiet [Savienojuma izveide ar Azure Data Lake Storage kontu ar Azure pakalpojuma primāro nosaukumu auditorijas ieskatiem](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Vides saites izveide

Varat izveidot vides saiti, atjauninot iestatījumus **Administrēšana** > **Vide** iesaistes ieskatos.

**Lai izveidotu aktīvu saiti starp auditorijas ieskatiem un iesaistes ieskatiem**

1. Lapā **Vides administrators** atlasiet cilni **Savienot vides**.

    :::image type="content" source="media/integrate1.png" alt-text="Vides iestatīšana.":::

1. Augšējā kreisajā stūrī vai ekrāna lejasdaļā atlasiet **Iestatīt vides**.

     :::image type="content" source="media/integrate2.png" alt-text="Auditorijas ieskatu vides atlase.":::

1. Atlasiet auditorijas ieskatu vidi un pēc tam atlasiet ***Tālāk**, lai pabeigtu. Tagad saistītajā vidē varat atlasīt neobligātos līdzekļus.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Iespējot auditorijas ieskatu vienotos profilu atribūtus un segmentus

Pēc saites izveides starp vidēm, saistītajā vidē varat atlasīt neobligātos līdzekļus. Šie līdzekļi iespējo vienotos profila atribūtus un segmentus no auditorijas ieskatiem interaktīvai klientu datu analīzei.

> [!IMPORTANT]
> Lai auditorijas ieskatu segmenti tiktu rādīti iesaistes ieskatos, vispirms ir [jāveic sapludināšana un lejupstraumes procesi](../audience-insights/merge-entities.md). Lejupstraumes procesi ir svarīgi, jo tie ģenerē unikālu tabulu, kas sagatavo auditorijas ieskatu segmentus, lai tos kopīgotu ar iesaistes ieskatiem. (Ja ir ieplānota sistēmas atsvaidzināšana, tajā automātiski tiks iekļauti lejupstraumes procesi.)

**Tīmekļa datu analīze iesaistes ieskatos**

1. Lapā **Vides administrators** ieslēdziet opciju **Kopīgot datus no auditorijas ieskatiem, izmantojot iesaistes ieskatus**, un pēc tam atlasiet opciju **Tālāk**.

    :::image type="content" source="media/integrate4.png" alt-text="Atlasīt līdzekļus.":::

1. Atlasiet vienoto profilu atribūtus, kas piesaistes ieskatos kļūs par papildu atribūtiem. (Ne visi atribūti ir noderīgas dimensijas. Piemēram, nav ticams, ka jums būtu nepieciešams **Vārds** vai **Uzvārds** kā atribūts jūsu vietnes notikumu analīzei.)

    :::image type="content" source="media/integrate5.png" alt-text="Pārraudzīt izmērus.":::

   >[!NOTE]
   > Visi auditorijas ieskatu profila atribūti, kas apzīmē identifikatorus (piemēram, **ID** un **alternatīvais ID**), tiek filtrēti no pieejamajiem atribūtiem un kļūst par piesaistes ieskatiem.

1. Pēc atribūtu atlasīšanas atlasiet **Tālāk**.
1. Pievienojiet lietotājus, kuri piesaistes ieskatos var apskatīt auditorijas ieskatu profilus un segmentus.

    :::image type="content" source="media/integrate6.png" alt-text="Piekļuves pārvaldīšana klientu datiem.":::

   > [!IMPORTANT]
   > Ja šajā darbībā tieši nevēlaties pievienot lietotājus, piesaistes ieskatos dati lietotājiem tiks slēpti.
   > Lai auditorijas ieskatu segmenti tiktu rādīti iesaistes ieskatos, vispirms ir [jāveic sapludināšana un lejupstraumes procesi](../audience-insights/merge-entities.md). Lejupstraumes procesi ir svarīgi, jo tie ģenerē unikālu tabulu, kas sagatavo auditorijas ieskatu segmentus, lai tos kopīgotu ar iesaistes ieskatiem. (Ja ir ieplānota sistēmas atsvaidzināšana, tajā automātiski tiks iekļauti lejupstraumes procesi.)

1. Pārskatiet atlasi un pēc tam atlasiet **Pabeigt**.

    :::image type="content" source="media/integrate7.png" alt-text="Pārskatiet klientu datu iestatījumus.":::

## <a name="export-refined-events-to-audience-insights"></a>Eksportēt precizētus notikumus auditorijas ieskatos

Kad būsiet izveidojis saiti starp vidēm, varat eksportēt precizētus notikumus no iesaistes ieskatiem uz auditorijas ieskatiem, un tos uzņemt kā jaunu datu avotu. 

Papildinformācijai skatiet [Tīmekļa datu integrēšana no iesaistes ieskatiem ar auditorijas ieskatiem](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
