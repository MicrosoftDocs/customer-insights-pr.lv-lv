---
title: Izmantojiet savu Azure Data Lake Storage Gen2 kontu
author: mukeshpo
description: Uzziniet par prasībām izmantot savu Azure Data Lake Storage kontu Customer Insights datu glabāšanai.
ms.author: mukeshpo
ms.date: 05/30/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 9fcd7645e34bf310ac3a1b98a0dd9a60598b19dc
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833949"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Izmantojiet savu Azure Data Lake Storage Gen2 kontu

Dynamics 365 Customer Insights dod iespēju saglabāt visus savus datus [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction).

Saglabājot datus Data Lake Storage, jūs piekrītat, ka dati tiks pārsūtīti un glabāti šim Azure krātuves kontam atbilstošajā ģeogrāfiskajā atrašanās vietā. Papildinformāciju skatiet [Microsoft drošības kontroles centrā](https://www.microsoft.com/trust-center).

Administratori customer insights var [izveidot vides](create-environment.md) un [norādīt datu glabāšanas opciju](create-environment.md#step-2-configure-data-storage) šajā procesā.

## <a name="prerequisites-to-use-your-storage-account"></a>Priekšnosacījumi krātuves konta izmantošanai

- Azure Data Lake Storage kontiem jāatrodas tajā pašā Debeszila reģionā, kuru atlasījāt, veidojot customer insights vidi. Customer Insights vides reģionu varat pārbaudīt sadaļā **Administrēšanas** > **sistēma** > **Par**.
- Datu ezera krātuvei jābūt Gen2 un jābūt iespējotai [hierarhiskai nosaukumvietai](/azure/storage/blobs/create-data-lake-storage-account). Gen1 krātuves konti netiek atbalstīti.
- Krātuves kontā ir jābūt norādītam `customerinsights` konteineram. Jums tas ir jāizveido, pirms izmantojat savu Datu ezera krātuvi customer insights. Administratoram, kas iestatījis Customer Insights vidi, krātuves kontā vai konteinerā ir nepieciešama krātuves BLOB datu līdzstrādnieka vai `customerinsights` krātuves BLOB datu īpašnieka loma. Papildinformāciju par atļauju piešķiršanu krātuves kontā skatiet rakstā [Krātuves konta](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal) izveide.

## <a name="connect-customer-insights-with-your-storage-account"></a>Customer Insights savienošana ar krātuves kontu

Veidojot jaunu vidi, pārliecinieties, vai datu ezera krātuves konts pastāv un visi priekšnosacījumi ir izpildīti.

1. **Datu glabāšanas** solī vides izveides laikā iestatiet **Saglabāt izvades** datus **Azure Data Lake Storage Gen2**.
1. Izvēlieties, **kā savienot krātuvi**. Varat izvēlēties opciju, kuras pamatā ir resursi, un autentifikācijas opciju, kuras pamatā ir abonements. Papildinformāciju skatiet rakstā [Savienojuma izveide ar Azure Data Lake Storage kontu, izmantojot Azure pakalpojuma direktoriju](connect-service-principal.md).
   - Azure abonementam **izvēlieties** abonements **·**, **resursu grupa** un **krātuves konts**, kurā atrodas konteiners`customerinsights`.
   - Konta atslēgai **norādiet** datu ezera **krātuves konta konta nosaukumu** un **konta atslēgu**. Šīs autentifikācijas metodes izmantošana nozīmē, ka esat informēts, ja jūsu organizācija pagriež atslēgas. Kad vides konfigurācija [ir pagriezta, tā ir jāatjaunina](manage-environments.md#edit-an-existing-environment) ar jauno atslēgu.

Kad sistēmas procesi, piemēram, datu uzņemšana ir pabeigta, sistēma izveido atbilstošas mapes krātuves kontā. Datu faili un *model.json* faili tiek izveidoti un pievienoti mapēm, pamatojoties uz procesa nosaukumu.

Ja izveidojat vairākas Customer Insights vides un vēlaties saglabāt izvades entītijas no šīm vidēm krātuves kontā, Customer Insights izveido atsevišķas mapes katrai videi, kuras saturs ir `ci_environmentID` konteiners.
