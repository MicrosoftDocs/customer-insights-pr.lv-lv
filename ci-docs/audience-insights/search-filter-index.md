---
title: Klientu profilu meklēšana un filtrēšana
description: Ātri atrodiet informāciju par vienotajiem klientu profiliem un filtrējiet norādītos atribūtus.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597152"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="ba034-103">Klientu profili: Meklēšanas un filtrēšanas indekss</span><span class="sxs-lookup"><span data-stu-id="ba034-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="ba034-104">Klientu datu apvienošanas rezultāts ir entītija Klientu profils, kas nodrošina vienotu skatu uz visu jūsu klientu bāzi.</span><span class="sxs-lookup"><span data-stu-id="ba034-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="ba034-105">Lai ātri [atrastu informāciju par konkrētu klientu vai klientu grupu](customer-profiles.md), varat konfigurēt **meklēšanas** un **filtrēšanas** iespējas lapā **Klienti**.</span><span class="sxs-lookup"><span data-stu-id="ba034-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="ba034-106">Tālāk uzzināsiet, kā administratori var rediģēt atribūtus lapā **Rādītāja meklēšana un filtrēšana**, ko lietotāji var izmantot meklēšanai un filtrēšanai.</span><span class="sxs-lookup"><span data-stu-id="ba034-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ba034-107">![Meklēšanas rezultātu filtrs](media/search-filter.png "Meklēšanas rezultātu filtrs")</span><span class="sxs-lookup"><span data-stu-id="ba034-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="ba034-108">Lauku pievienošana un atribūtu norādīšana</span><span class="sxs-lookup"><span data-stu-id="ba034-108">Add fields and specify attributes</span></span>

<span data-ttu-id="ba034-109">Ja šī ir pirmā reize, kad definējat meklējamos atribūtus kā administrators, vispirms ir jādefinē indeksētie lauki.</span><span class="sxs-lookup"><span data-stu-id="ba034-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="ba034-110">Ieteicams izvēlēties visus atribūtus, pēc kuriem lietotāji var meklēt un filtrēt klientus lapā **Klienti**.</span><span class="sxs-lookup"><span data-stu-id="ba034-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="ba034-111">Ir iespējams norādīt tikai tos atribūtus, kas pastāv entītijā Klienta profils, ko izveidojāt datu apvienošanas procesā.</span><span class="sxs-lookup"><span data-stu-id="ba034-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="ba034-112">Atveriet lapu **Klienti** un atlasiet **Meklēšanas un filtra indekss**.</span><span class="sxs-lookup"><span data-stu-id="ba034-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="ba034-113">Atlasiet **+ Pievienot**, lai precizētu indeksētos laukus.</span><span class="sxs-lookup"><span data-stu-id="ba034-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="ba034-114">Sarakstā atlasiet atribūtus, kurus vēlaties pievienot kā indeksētos laukus.</span><span class="sxs-lookup"><span data-stu-id="ba034-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="ba034-115">Jūs jebkurā laikā varat pievienot papildu atribūtus, atlasot **Pievienot**.</span><span class="sxs-lookup"><span data-stu-id="ba034-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="ba034-116">Varat arī noņemt jebkurus atlasītos atribūtus, atzīmējot **Noņemt** simbolu.</span><span class="sxs-lookup"><span data-stu-id="ba034-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="ba034-117">Tabulas Indeksētie klienta lauki izpēte</span><span class="sxs-lookup"><span data-stu-id="ba034-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="ba034-118">Šajā tabulā ir pieejama tālāk norādītā informācija.</span><span class="sxs-lookup"><span data-stu-id="ba034-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="ba034-119">**Nosaukums**: norāda atribūta nosaukumu, kāds tas tiek rādīts entītija Klienta profils.</span><span class="sxs-lookup"><span data-stu-id="ba034-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="ba034-120">**Datu tips**: norāda, vai datu tips ir virkne, skaitlis vai datums.</span><span class="sxs-lookup"><span data-stu-id="ba034-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="ba034-121">**Iekļauts meklēšanā**: norāda, vai šo atribūtu var izmantot, lai meklētu klientus lapā **Klienti**, izmantojot **meklēšanas** lauku.</span><span class="sxs-lookup"><span data-stu-id="ba034-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="ba034-122">**Pievienot filtru**: vadīkla, lai definētu, kā šo atribūtu var izmantot filtrēšanai lapā **Klienti**.</span><span class="sxs-lookup"><span data-stu-id="ba034-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="ba034-123">Filtrēšanas opciju rediģēšana noteiktam atribūtam</span><span class="sxs-lookup"><span data-stu-id="ba034-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="ba034-124">Lapas **Klienti** izvēlnē **Filtrēt** var būt ietverts atšķirīgs atribūtu līmeņu skaits (piemēram, dažādas vecuma grupas, pēc kurām filtrēt klientus).</span><span class="sxs-lookup"><span data-stu-id="ba034-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="ba034-125">Atlasiet **Pievienot filtru** konkrētajam atribūtam lapā **Rādītāja meklēšana un filtrēšana**.</span><span class="sxs-lookup"><span data-stu-id="ba034-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="ba034-126">Varat noteikt rezultātu skaitu un secību, kādā tie tiks sakārtoti.</span><span class="sxs-lookup"><span data-stu-id="ba034-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="ba034-127">Atkarībā no atribūta datu tipa tiek rādīta viena no tālāk redzamajām rūtīm.</span><span class="sxs-lookup"><span data-stu-id="ba034-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="ba034-128">Virknes tipa atribūts: norādiet vēlamo rezultātu skaitu rūtī **Virknes filtrēšanas opcijas** un rezultātu rādīšanas secības politiku.</span><span class="sxs-lookup"><span data-stu-id="ba034-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="ba034-129">Skaitliska tipa atribūts: norādiet iekļaujamo intervālu rūtī **Skaitļa filtrēšanas opcijas** un rezultātu rādīšanas secības politiku.</span><span class="sxs-lookup"><span data-stu-id="ba034-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="ba034-130">Datuma tipa atribūts: norādiet iekļaujamo intervālu rūtī **Datuma filtrēšanas opcijas** un rezultātu rādīšanas secības politiku.</span><span class="sxs-lookup"><span data-stu-id="ba034-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="ba034-131">Lai veiktās izmaiņas stātos spēkā, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="ba034-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="ba034-132">Kad būsiet gatavs lietot iestatījumus, atlasiet **Palaist**.</span><span class="sxs-lookup"><span data-stu-id="ba034-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ba034-133">Nākamās darbības</span><span class="sxs-lookup"><span data-stu-id="ba034-133">Next steps</span></span>

<span data-ttu-id="ba034-134">Dodieties uz lapu **Klienti**, lai meklētu klientu profilus vai izmantotu indeksētos laukus, lai skatītu visu klientu profilu apakškopu.</span><span class="sxs-lookup"><span data-stu-id="ba034-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]