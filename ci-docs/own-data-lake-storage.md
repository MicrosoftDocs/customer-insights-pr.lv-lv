---
title: Izmantojiet savu Azure Data Lake Storage Gen2 kontu
author: mukeshpo
description: Uzziniet par prasībām izmantot savu Azure Data Lake Storage kontu, lai glabātu Customer Insights datus.
ms.author: mukeshpo
ms.date: 08/15/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5e4b9348f06d4e5e10b4499ad86b38c9d52da1f5
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304390"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Izmantojiet savu Azure Data Lake Storage Gen2 kontu

Dynamics 365 Customer Insights dod jums iespēju saglabāt visus savus datus [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction). Saglabājot datus Data Lake Storage, jūs piekrītat, ka dati tiks pārsūtīti un glabāti šim Azure krātuves kontam atbilstošajā ģeogrāfiskajā atrašanās vietā. Papildinformāciju skatiet sadaļā [Microsoft drošības kontroles centrs](https://www.microsoft.com/trust-center).

Administratori programmā Customer Insights var [izveidot vides](create-environment.md) un [norādīt datu glabāšanas opciju](create-environment.md#step-2-configure-data-storage) šajā procesā.

## <a name="prerequisites"></a>Priekšnoteikumi

- Azure Data Lake Storage kontiem ir jāatrodas tajā pašā Azure reģionā, kuru atlasījāt, veidojot Customer Insights vidi. Lai uzzinātu vides reģionu, dodieties uz **administrēšanas** > **sistēma** > **par** programmā Customer Insights.
- Datu ezera krātuves kontam jābūt Gen2. Azure Data Lake Gen1 krātuves konti netiek atbalstīti.
- Datu ezera krātuves kontā ir [jābūt hierarhiskai nosaukumvietai](/azure/storage/blobs/data-lake-storage-namespace).
- Krātuves kontā ir jābūt nosauktam `customerinsights` konteineram. Izveidojiet to, pirms izmantojat savu Datu ezera krātuvi programmā Customer Insights.
- Administratoram, kas iestata Customer Insights vidi, krātuves kontā vai konteinerā ir nepieciešama krātuves Blob datu līdzstrādnieka vai `customerinsights` krātuves Blob datu īpašnieka loma. Papildinformāciju par atļauju piešķiršanu krātuves kontā skatiet sadaļā [Krātuves konta](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal) izveide.

## <a name="connect-customer-insights-with-your-storage-account"></a>Customer Insights savienošana ar krātuves kontu

Veidojot jaunu vidi, pārliecinieties, vai datu ezera krātuves konts pastāv un vai ir izpildīti visi priekšnosacījumi.

1. **Darbībā Datu glabāšana** vides izveides laikā iestatiet opciju **Saglabāt izvades datus** uz **Azure Data Lake Storage Gen2**.
1. Izvēlieties, kā savienot **krātuvi**. Varat izvēlēties starp resursu opciju un abonēšanas opciju autentifikācijai. Papildinformāciju skatiet rakstā [Savienojuma izveide ar Azure Data Lake Storage kontu, izmantojot Azure pakalpojumu principālu](connect-service-principal.md).
   - Azure **abonementam** izvēlieties **abonementu**, **resursu grupu** un **krātuves kontu**, kurā ir konteiners`customerinsights`.
   - Laukā **Konta atslēga** norādiet **konta nosaukumu** un **konta atslēgu** Data Lake Storage kontam. Izmantojot šo autentifikācijas metodi, jūs esat informēts, ja jūsu organizācija pagriež atslēgas. [Pagriežot, ir jāatjaunina vides konfigurācija](manage-environments.md#edit-an-existing-environment) ar jauno taustiņu.
1. Izvēlieties, vai vēlaties izmantot Azure privāto saiti, lai izveidotu savienojumu ar krātuves kontu un [izveidotu savienojumu ar privāto saiti](security-overview.md#set-up-an-azure-private-link).

Kad sistēmas procesi, piemēram, datu norīšana, ir pabeigta, sistēma krātuves kontā izveido atbilstošas mapes. Datu faili un model.json faili tiek izveidoti un pievienoti mapēm, pamatojoties uz procesa nosaukumu.

Ja izveidojat vairākas Customer Insights vides un vēlaties saglabāt izvades entītijas no šīm vidēm krātuves kontā, Customer Insights izveido atsevišķas mapes katrai videi, kuras saturs ir `ci_environmentID` konteiners.
