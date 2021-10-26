---
title: Datu apvienošanas entītiju un atribūtu kartēšana
description: Atlasiet entītijas, atribūtus, primārās atslēgas un stiskus tipus, lai kartētu datus uz vienoto klienta profilu.
ms.date: 10/18/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-map
ms.openlocfilehash: 7ee3feea8423f35f32ff471b3ed8eb3447584089
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648171"
---
# <a name="map-entities-and-attributes"></a>Kartējiet entītijas un atribūtus

**Karte** ir pirmais posms auditorijas ieskatu datu apvienošanas procesā. Kartēšana sastāv no trim posmiem:

- *Entītijas atlase*: Norādiet savienojamās entītijas, kas aizved pie datu kopas ar pilnīgāku informāciju par jūsu klientiem.
- *Atribūtu atlase*: katrai entītijai norādiet kolonnas, ko vēlaties kombinēt un saskaņot *atbilstības noteikšanas* un *sapludināšanas* posmos. Šīs kolonnas sauc par *Atribūtiem*.
- *Primārā atslēga un semantiskā tipa atlase*: Katrai entītijai norādiet atribūtu, ko vēlaties definēt kā šīs entītijas primāro atslēgu, un katram atribūtam norādiet semantisko tipu, kas vislabāk raksturo šo atribūtu.

Papildinformāciju par datu apvienošanās vispārīgo plūsmu skatiet rakstā [Apvienošana](data-unification.md).

## <a name="select-the-first-entities"></a>Pirmo entītiju atlase

1. Sadaļā Auditorijas ieskati ejiet uz **Dati** > **Apvienot** > **Kartēt**.

2. Sāciet kartēšanas posmu, atlasot **Atlasīt entītijas**.

3. Atlasiet entītijas un atribūtus, ko vēlaties izmantot posmos *saskaņot* un *sapludināt*. No entītijas varat atlasīt nepieciešamos atribūtus pa vienam vai iekļaut visus, entītijas līmenī atlasot izvēles rūtiņu **Iekļaut visus laukus**. Lai gūtu labumu no datu apvienošanas procesa, ieteicams atlasīt vismaz divas entītijas.

   > [!div class="mx-imgBorder"]
   > ![Entītiju pievienošanas piemērs.](media/data-manager-configure-map-add-entities-example.png "Entītiju pievienošanas piemērs")

   Šajā piemērā mēs pievienojam entītijas **eCommerceContacts** un **loyCustomers**. Izvēloties šīs entītijas, varat gūt ieskatu par to, kuri tiešsaistes biznesa klienti ir lojalitātes programmas dalībnieki.
   
   Visos atribūtos un entītijās varat meklēt atslēgvārdus, lai atlasītu nepieciešamos atribūtus, ko vēlaties kartēt.
   
     > [!div class="mx-imgBorder"]
   > ![Meklēšanas lauku piemērs.](media/data-manager-configure-map-search-fields-example.png "Meklēšanas lauku piemērs")

4. Atlasiet **Lietot**, lai apstiprinātu atlasi.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Atribūtu primārās atslēgas un semantiskā tipa atlasīšana

Pēc entītiju atlasīšanas lapā **Kartēšana** pārbaudei ir uzskaitītas atlasītās entītijas. Definējiet entītijas primāro atslēgu un nosakiet entītijas atribūta semantisko tipu.

- **Primārā atslēga**: atlasiet vienu atribūtu kā primāro atslēgu katrai entītijai. Lai atribūts būtu derīga primārā atslēga, tajā nedrīkst ietvert vērtību dublikātus, trūkstošās vērtības vai nulles vērtības. Virknes, vesela skaitļa un GUID datu tipu atribūti tiek atbalstīti kā primārās atslēgas un tiks parādīti laukā, no kura iespējams veikt atlasi.

- **Atribūta semantiskais tips**: Jūsu atribūtu kategorijas, piemēram, e-pasta adrese vai nosaukums. Lai semantikas viedajai prognozēšanai izmantotu mākslīgā intelekta modeļus, ietaupītu laiku un uzlabotu precizitāti, iestatiet **Inteliģento kartēšanu** uz pozīciju **ON**. Inteliģentā kartēšana izceļ mākslīgā intelekta semantikas ieteikumu laukā **Veids**. Ja to iestatāt uz pozīciju **OFF**, jūs redzēsit regulāros kartēšanas ieteikumus. No pieejamā opciju saraksta varat atlasīt jebkuru semantisko veidu un pārlabot esošo atlasi.

> [!div class="mx-imgBorder"]
> ![Atribūta veids un semantiskā prognoze.](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Atribūta veids un semantiskā prognoze")

Ir iespējams pievienot arī pielāgotu semantisko tipu. Atlasiet atribūta lauka tipu un ierakstiet pielāgotā semantiskā atribūta tipa nosaukumu. Tādējādi varat arī mainīt sistēmas noteiktos atribūtu tipus.

Visi atribūti, kam automātiski tiek noteikts semantiskais tips, tiek grupēti sadaļā **Pārbaudīt kartētos laukus**. Pārbaudiet šos atribūtus un to semantiskos tipus, jo tie tiks izmantoti, lai apvienotu jūsu entītijas datu apvienošanas sapludināšanas darbībā.

Atribūti, kas netiek automātiski kartēti uz semantisko tipu, tiek grupēti sadaļā **Definēt datus nekartētajos laukos**. Atlasiet nekartēto atribūtu semantisko tipu lauku vai ievadiet savu pielāgoto atribūta tipa nosaukumu.

> [!div class="mx-imgBorder"]
> ![Primārā atslēga un atribūta tips.](media/data-manager-configure-map-add-attributes.png "Primārā atslēga un atribūta tips")

> [!NOTE]
> Viens lauks ir jākartē uz semantisko tipu Person.FullName, lai klienta kartē aizpildītu klienta vārdu. Pretējā gadījumā klientu kartes tiks rādītas kā anonīmas. 

## <a name="add-and-remove-attributes-and-entities"></a>Atribūtu un entītiju pievienošana un noņemšana

1. Sadaļā **Apvienot** > **Kartēšana**, atlasiet **Rediģēt laukus**.

2. Rūtī **Rediģēt laukus** pievienojiet vai noņemiet atribūtus un entītijas. Izmantojiet meklēšanu vai ritiniet, lai atrastu un atlasītu interesējošos atribūtus un entītijas. Nevar noņemt atribūtu vai entītiju, ja tie jau ir saskaņoti.

   > [!div class="mx-imgBorder"]
   > ![Atribūtu pievienošana vai noņemšana.](media/configure-data-map-edit.png "Atribūtu pievienošana vai noņemšana")

3. Atlasiet vienumu **Piemērot**.

## <a name="add-images-to-profiles"></a>Pievienojiet profiliem attēlus

Ja entitīja satur vietrāžus URL uz publiski pieejamiem profila attēliem vai logotipiem, varat tos pievienot vienotajam klienta profilam.

Atlasiet entitīju un atrodiet lauku, kas satur vietrādi URL uz profila attēlu. Ievades laukā **Veids** manuāli ievadiet tālāk norādīto vērtību: 
- Personai: Person.ProfileImage
- Organizācijai: Organization.LogoImage

Turpiniet ar apvienošanās darbībām un nodrošiniet, ka darbībā [Sapludināt](merge-entities.md) tiek pievienots arī atribūts, kas satur attēla URL.

## <a name="set-attributes-for-organizations"></a>Atribūtu iestatīšana organizācijām

Organizācijām (priekšskatījums) atribūta tipam ir jābūt kartētam uz “Organization.Name”.
> [!div class="mx-imgBorder"]
> ![Primārā atslēga un atribūta tips B2B](media/configure-data-map-edit-b2b.png "Primārā atslēga un atribūta tips B2B")

## <a name="next-step"></a>Nākamā darbība

Datu apvienošanas procesa ietvaros pārejiet uz lapu **Atbilstība**. Apmeklējiet rakstu [**Atbilstība**](match-entities.md), lai uzzinātu par šo posmu.

> [!TIP]
> Noskatieties šo videoklipu: [Darba sākšana: vienota klienta profila izveide](https://youtu.be/oBfGEhucAxs).


[!INCLUDE[footer-include](../includes/footer-banner.md)]