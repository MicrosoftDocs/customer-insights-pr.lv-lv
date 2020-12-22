---
title: Klientu profilu meklēšana un filtrēšana
description: Ātri atrodiet informāciju par vienotajiem klientu profiliem un filtrējiet norādītos atribūtus.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406367"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="60c16-103">Klientu profili: Meklēšanas un filtrēšanas indekss</span><span class="sxs-lookup"><span data-stu-id="60c16-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="60c16-104">Klientu datu apvienošanas rezultāts ir entītija Klientu profils, kas nodrošina vienotu skatu uz visu jūsu klientu bāzi.</span><span class="sxs-lookup"><span data-stu-id="60c16-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="60c16-105">Lai ātri [atrastu informāciju par konkrētu klientu vai klientu grupu](customer-profiles.md), varat konfigurēt **meklēšanas** un **filtrēšanas** iespējas lapā **Klienti**.</span><span class="sxs-lookup"><span data-stu-id="60c16-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="60c16-106">Tālāk uzzināsiet, kā administratori var rediģēt atribūtus lapā **Rādītāja meklēšana un filtrēšana**, ko lietotāji var izmantot meklēšanai un filtrēšanai.</span><span class="sxs-lookup"><span data-stu-id="60c16-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="60c16-107">![Meklēšanas rezultātu filtrs](media/search-filter.png "Meklēšanas rezultātu filtrs")</span><span class="sxs-lookup"><span data-stu-id="60c16-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="60c16-108">Lauku pievienošana un atribūtu norādīšana</span><span class="sxs-lookup"><span data-stu-id="60c16-108">Add fields and specify attributes</span></span>

<span data-ttu-id="60c16-109">Ja šī ir pirmā reize, kad definējat meklējamos atribūtus kā administrators, vispirms ir jādefinē indeksētie lauki.</span><span class="sxs-lookup"><span data-stu-id="60c16-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="60c16-110">Ieteicams izvēlēties visus atribūtus, pēc kuriem lietotāji var meklēt un filtrēt klientus lapā **Klienti**.</span><span class="sxs-lookup"><span data-stu-id="60c16-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="60c16-111">Ir iespējams norādīt tikai tos atribūtus, kas pastāv entītijā Klienta profils, ko izveidojāt datu apvienošanas procesā.</span><span class="sxs-lookup"><span data-stu-id="60c16-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="60c16-112">Atveriet lapu **Klienti** un atlasiet **Meklēšanas un filtra indekss**.</span><span class="sxs-lookup"><span data-stu-id="60c16-112">Open the **Customers** page and select **Search & filter index**.</span></span>

> [!NOTE]
> <span data-ttu-id="60c16-113">Noklusējuma meklēšanas indeksa konfigurāciju var izveidot Klienta entītijā pieejamajos atribūtos, izmantojot tālāk norādītos semantiskos tipus, kā tas ir definēts Kartes lapā.</span><span class="sxs-lookup"><span data-stu-id="60c16-113">We create a default search index configuration on the available attributes in the Customer entity from the following semantic types as defined on the Map page.</span></span>
> - <span data-ttu-id="60c16-114">Personas vārds, uzvārds, otrais vārds, pilns vārds un uzvārds</span><span class="sxs-lookup"><span data-stu-id="60c16-114">Person First name, Last name, Middle name, Full Name</span></span>
> - <span data-ttu-id="60c16-115">Organizācijas nosaukums</span><span class="sxs-lookup"><span data-stu-id="60c16-115">Organization Name</span></span>
> - <span data-ttu-id="60c16-116">E-pasta adrese</span><span class="sxs-lookup"><span data-stu-id="60c16-116">Email address</span></span>
> - <span data-ttu-id="60c16-117">Tālruņa numurs</span><span class="sxs-lookup"><span data-stu-id="60c16-117">Phone number</span></span>
> - <span data-ttu-id="60c16-118">Atrašanās vietas informācija</span><span class="sxs-lookup"><span data-stu-id="60c16-118">Location information</span></span>

2. <span data-ttu-id="60c16-119">Atlasiet **+ Pievienot**, lai precizētu indeksētos laukus.</span><span class="sxs-lookup"><span data-stu-id="60c16-119">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="60c16-120">Sarakstā atlasiet atribūtus, kurus vēlaties pievienot kā indeksētos laukus.</span><span class="sxs-lookup"><span data-stu-id="60c16-120">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="60c16-121">Jūs jebkurā laikā varat pievienot papildu atribūtus, atlasot **Pievienot**.</span><span class="sxs-lookup"><span data-stu-id="60c16-121">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="60c16-122">Varat arī noņemt jebkurus atlasītos atribūtus, atzīmējot **Noņemt** simbolu.</span><span class="sxs-lookup"><span data-stu-id="60c16-122">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="60c16-123">Tabulas Indeksētie klienta lauki izpēte</span><span class="sxs-lookup"><span data-stu-id="60c16-123">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="60c16-124">Šajā tabulā ir pieejama tālāk norādītā informācija.</span><span class="sxs-lookup"><span data-stu-id="60c16-124">The following information is presented in the table.</span></span>

- <span data-ttu-id="60c16-125">**Nosaukums**: norāda atribūta nosaukumu, kāds tas tiek rādīts entītija Klienta profils.</span><span class="sxs-lookup"><span data-stu-id="60c16-125">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="60c16-126">**Datu tips**: norāda, vai datu tips ir virkne, skaitlis vai datums.</span><span class="sxs-lookup"><span data-stu-id="60c16-126">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="60c16-127">**Iekļauts meklēšanā**: norāda, vai šo atribūtu var izmantot, lai meklētu klientus lapā **Klienti**, izmantojot **meklēšanas** lauku.</span><span class="sxs-lookup"><span data-stu-id="60c16-127">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="60c16-128">**Pievienot filtru**: vadīkla, lai definētu, kā šo atribūtu var izmantot filtrēšanai lapā **Klienti**.</span><span class="sxs-lookup"><span data-stu-id="60c16-128">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="60c16-129">Filtrēšanas opciju rediģēšana noteiktam atribūtam</span><span class="sxs-lookup"><span data-stu-id="60c16-129">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="60c16-130">Lapas **Klienti** izvēlnē **Filtrēt** var būt ietverts atšķirīgs atribūtu līmeņu skaits (piemēram, dažādas vecuma grupas, pēc kurām filtrēt klientus).</span><span class="sxs-lookup"><span data-stu-id="60c16-130">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="60c16-131">Atlasiet **Pievienot filtru** konkrētajam atribūtam lapā **Rādītāja meklēšana un filtrēšana**.</span><span class="sxs-lookup"><span data-stu-id="60c16-131">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="60c16-132">Varat noteikt rezultātu skaitu un secību, kādā tie tiks sakārtoti.</span><span class="sxs-lookup"><span data-stu-id="60c16-132">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="60c16-133">Atkarībā no atribūta datu tipa tiek rādīta viena no tālāk redzamajām rūtīm.</span><span class="sxs-lookup"><span data-stu-id="60c16-133">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="60c16-134">Virknes tipa atribūts: norādiet vēlamo rezultātu skaitu rūtī **Virknes filtrēšanas opcijas** un rezultātu rādīšanas secības politiku.</span><span class="sxs-lookup"><span data-stu-id="60c16-134">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="60c16-135">Skaitliska tipa atribūts: norādiet iekļaujamo intervālu rūtī **Skaitļa filtrēšanas opcijas** un rezultātu rādīšanas secības politiku.</span><span class="sxs-lookup"><span data-stu-id="60c16-135">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="60c16-136">Datuma tipa atribūts: norādiet iekļaujamo intervālu rūtī **Datuma filtrēšanas opcijas** un rezultātu rādīšanas secības politiku.</span><span class="sxs-lookup"><span data-stu-id="60c16-136">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="60c16-137">Lai veiktās izmaiņas stātos spēkā, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="60c16-137">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="60c16-138">Kad būsiet gatavs lietot iestatījumus, atlasiet **Palaist**.</span><span class="sxs-lookup"><span data-stu-id="60c16-138">Select **Run** once you're ready to apply your settings.</span></span>
