---
title: Vienotu profilu izmantošana programmā Dynamics 365 Marketing
description: Uzziniet, kā integrēt vienotos profilus un segmentus pakalpojumā Dynamics 365 Marketing.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4cc3cbde97d0f9da198652e86c0843476393b646
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833317"
---
# <a name="work-with-unified-customer-profiles-in-dynamics-365-marketing"></a>Darbs ar vienotiem klientu profiliem programmā Dynamics 365 Marketing

[Dynamics 365 Marketing](/dynamics365/marketing/overview) paaugstina klientu pieredzi, ļaujot organizēt personalizētus ceļojumus visos saskares punktos, lai stiprinātu attiecības un nopelnītu lojalitāti. Dynamics 365 Marketing programma darbojas nevainojami ar Dynamics 365 Sales, un citiem produktiem un ļauj pieņemt ātrākus un labākus lēmumus, Dynamics 365 Customer Insights Microsoft Teams izmantojot datu un MĀKSLĪGĀ INTELEKTA iespējas.

Savienojot Customer Insights datus ar mārketingu, varat:

- Atlasīt vienotos klientu profilus un segmentus. Tas ļauj piesaistīt ikvienu klientu neatkarīgi no klienta datu atrašanās vietas.
- Pamata dinamiskais saturs (piemēram, personalizēti žetoni) e-pasta ziņojumos, īsziņās un pašpiegādes paziņojumos par tādiem pasākumiem kā lojalitātes programmas statuss, abonementa atjaunošanas datums, galvenais uzņēmums vai jebkurš cits pasākums, ko esat iemūžinājis vienotajā Customer Insights profilā.
- Ielādējiet mārketinga datus Customer Insights un apvienojiet tos ar klientu datiem no citiem avotiem.
- Izmantojiet Customer Insights datu tīrīšanas, bagātināšanas un izplūdušo atbilstības rīkus.

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Bagātīgu klientu profilu izmantošana reāllaika mārketingā

Reāllaika mārketings ļauj izveidot [pielāgotus trigerus](/dynamics365/marketing/real-time-marketing-custom-triggers), kas uzsāk klientu braucienus, pamatojoties uz jebkuru klientu darbību. Jo personalizētāki būs jūsu dati, jo atbilstošāki un personalizētāki būs jūsu ceļojumi. Tas padara mārketinga un klientu ieskatu apvienošanu tik spēcīgu. Jūs varat [apvienot datus](data-unification.md) no jebkura avota, pēc tam izmantot tos, lai veicinātu hiperpersonalizētus klientu braucienus.

Papildinformācija: [Customer Insights profilu un segmentu izmantošana reāllaika mārketingā](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Izmantot vienotus segmentus ar izejošajiem klientu braucieniem

Customer Insights ļauj precizēt datus no daudziem avotiem un apvienot tos apkopotos klientu segmentos. Savienojot [Customer Insights ar izejošo mārketingu](export-dynamics365-marketing.md), šie segmenti automātiski parādīsies *un* tiks automātiski atsvaidzināti automatizēta kampaņa noformētājā.

Papildinformācija: [Segmentu izmantošana pakalpojumā Dynamics 365 Customer Insights Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Pavelciet datus no sava Azure Data Lake Storage

Jūs neaprobežojaties tikai ar mākoņkrātuvi, ja vēlaties izmantot Customer Insights datus ar mārketingu. Ja jums jau ir sava Azure Data Lake Storage iestatīšana, varat izveidot savienojumu ar Customer Insights, pēc tam kopīgot datus ar lietotni Mārketings tāpat kā ar mākonī balstītu iestatījumu.

Papildinformācija: [Datu kopīgošanas iespējošana no Dataverse savas Azure Data Lake Storage](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)
