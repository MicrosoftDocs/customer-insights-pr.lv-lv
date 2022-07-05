---
title: Vienotu profilu izmantošana programmā Dynamics 365 Marketing
description: Uzziniet, kā integrēt vienotus profilus un segmentus ar Dynamics 365 Marketing.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99ec463299a24ea81cfe26bb785e36bdefdcd080
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054441"
---
# <a name="use-unified-customer-profiles-in-dynamics-365-marketing"></a>Vienotu klientu profilu izmantošana programmā Dynamics 365 Marketing

[Dynamics 365 Marketing](/dynamics365/marketing/overview) uzlabo klientu pieredzi, ļaujot jums organizēt personalizētus ceļojumus visos saziņas punktos, lai stiprinātu attiecības un nopelnītu lojalitāti. Programma Dynamics 365 Marketing nemanāmi darbojas ar Dynamics 365 Sales,, Dynamics 365 Customer Insights un citiem produktiem un ļauj pieņemt ātrākus un labākus lēmumus, Microsoft Teams izmantojot datu un AI iespējas.

Savienojot Customer Insights datus ar Marketing, varat:

- Mērķējiet uz vienotiem klientu profiliem un segmentiem. Tas ļauj jums piesaistīt ikvienu klientu neatkarīgi no klienta datu atrašanās vietas.
- Bāziet dinamisku saturu (piemēram, personalizētus marķierus) e-pasta ziņojumos, īsziņās un pašpiegādes paziņojumos par tādiem pasākumiem kā lojalitātes statuss, abonēšanas atjaunošanas datums, galvenais uzņēmums vai jebkurš cits pasākums, ko esat tveris vienotajā Customer Insights profilā.
- Ielādējiet marketing datus programmā Customer Insights un apvienojiet tos ar klientu datiem no citiem avotiem.
- Izmantojiet Customer Insights datu tīrīšanas, bagātināšanas un izplūdušus saskaņošanas rīkus.

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Bagātu klientu profilu izmantošana reāllaika mārketingā

Reāllaika mārketings ļauj izveidot [pielāgotus trigerus](/dynamics365/marketing/real-time-marketing-custom-triggers), kas uzsāk automatizētās kampaņas, pamatojoties uz jebkuru klienta darbību. Jo personalizētāki būs jūsu dati, jo atbilstošāki un personalizētāki būs jūsu ceļojumi. Tas padara marketing un customer insights apvienošanu tik jaudīgu. [Varat apvienot datus](data-unification.md) no jebkura avota un pēc tam tos izmantot, lai veicinātu hiperpersonalizētas automatizētas automatizētas automatizētas automatizētas kampaņas ar klientiem.

Papildinformācija: [Customer Insights profilu un segmentu izmantošana reāllaika mārketingā](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Vienotu segmentu izmantošana izejošajām automatizētajām kampaņām

Customer Insights ļauj precizēt datus no daudziem avotiem un apvienot tos apkopotos klientu segmentos. Savienojot [Customer Insights ar izejošo mārketingu](export-dynamics365-marketing.md), šie segmenti automātiski parādīsies *un* tiks automātiski atsvaidzināti automatizēta kampaņa noformētājā.

Papildinformācija: [segmentu izmantošana no Dynamics 365 Customer Insights Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Iegūstiet datus no sava Azure Data Lake Storage

Jūs neaprobežojaties tikai ar mākoņkrātuvi, ja vēlaties izmantot Customer Insights datus programmā Marketing. Ja jums jau ir savs Azure Data Lake Storage iestatījums, varat izveidot savienojumu, izmantojot Customer Insights, un pēc tam kopīgot datus ar programmu Mārketings tāpat kā ar mākoņa iestatījumu.

Papildinformācija: [Datu kopīgošanas iespējošana, izmantojot Dataverse savus lietotājus Azure Data Lake Storage](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)
