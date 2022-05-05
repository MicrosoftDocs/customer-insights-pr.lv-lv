---
title: Darba sākšana ar uzņēmuma uzņēmumiem kā primārā mērķa auditorija
description: Darba sākšana ar uzņēmuma uzņēmumiem kā primārā mērķa auditorija programmā Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: f16c8ad50ed290562fa9f223a3e8c86228e5331e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643475"
---
# <a name="work-with-business-accounts"></a>Darbs ar uzņēmuma kontiem

Ļauj Dynamics 365 Customer Insights konfigurēt vidi dažādām primārajām mērķauditorijām: individuāliem patērētājiem (no B-C līdz C) un biznesa kontiem (no B-līdz B). B2C scenārijos dati tiek centrēti uz atsevišķiem indivīdiem. B2B vajadzībām primārā mērķa auditorija ir uzņēmumi - organizācijas vai uzņēmumi - un kontaktpersonas. Šis raksts palīdz sākt darbu ar uzņēmumu kontu vidi. Tajā ir uzskaitītas klientu ieskatu līdzekļu apgabalu atšķirības atkarībā no jūsu vides fokusa. Lai iegūtu papildinformāciju par atšķirībām, pārskatiet līdzekļu apgabalu dokumentus. 

## <a name="create-an-environment-for-business-accounts"></a>Vides izveide uzņēmuma kontiem

Administratori var [izveidot vidi esošā organizācijā](create-environment.md). Jaunas vides izveides procesā notiek darbība, kurā administratoriem tiek lūgts izmantot vides primāro mērķa auditoriju. Gadījumā, ja tas ir sākotnējais iestatījums pēc licences iegādes, vadīta pieredze palīdz izveidot pirmo vidi.

Pēc tam varat [izgūt datus](data-sources.md) uzņēmumu kontiem un saistītajām kontaktpersonām kā datu avotus no visiem atbalstītajiem avotiem.

Pēc datu vienošanas [norādiet uzņēmumu hierarhijas](relationships.md#set-up-account-hierarchies) kā daļu no attiecību konfigurācijas. Varat arī [konfigurēt semantiskos kartējumus](semantic-mappings.md), lai izveidotu kontaktpersonu un uzņēmumu entītiju savienojumu. 

## <a name="switch-between-primary-target-audience"></a>Pārslēgties starp primāro mērķa auditoriju

Ja jūsu organizācija uztur vidi atsevišķiem klientiem un biznesa uzņēmumiem, varat kreisajā rūtī lietot pārslēdzēju, lai izvēlētos primāro mērķa mērķauditoriju.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Pārslēdzējs, lai mainītu primāro mērķa auditoriju starp atsevišķiem klientiem un biznesa uzņēmumiem.":::

## <a name="supported-feature-areas"></a>Atbalstīto līdzekļu reģioni

- [Darbības](activities.md): atbalsts uzņēmumiem un saistītām kontaktpersonām, lai izveidotu darbības un rādītu tās laika skalā.
- [Attiecības](relationships.md): darbību vednis palīdz izveidot attiecības starp entītijām, lai uzņēmuma skatā varētu tikt parādītas visas kontaktpersonu darbības. Kontaktpersonas var rakties kontakta skatā, un hierarhijas var tikt izmantotas uzņēmuma darbību apkopošanai.
- [Pasākumi](measures.md): atbalsta pasākumus, kas izveidoti no pasākumu veidotāja ar vienu aprēķinu. Ja iestatījums nav obligāts, veicot pasākumu izveidi, tiek atļauts apkopot pakārtotos uzņēmumus.
- [Segmenti](segments.md): atbalsta segmentus, kas izveidoti no tukšas veidlapas ar segmentu veidotāju. Veidojot segmentus, jauni operatori atļauj kontu hierarhiju.
- [Datu izgūšana](data-sources.md): visi līdzekļi šajā apgabalā uzņēmumu kontiem un atsevišķiem klientiem ir vienādi.
- [Datu apvienošana](data-unification.md): visi līdzekļi šajā apgabalā uzņēmumu kontiem un atsevišķiem klientiem ir vienādi.
- [Bagātināšana](enrichment-hub.md): daži bagātināšanas tipi ir pieejami tikai atsevišķiem klientu scenārijiem, bet pārējie ir pieejami tikai biznesa uzņēmumiem.
- [Atbalsta meklētājs un iepriekš pieejami modeļi](predictions-overview.md): transakciju prognoze ietver papildu darbības uzņēmuma kontiem. Citas prognozes iespējas ir pieejamas tikai atsevišķiem klientiem.
- [Aktivizēšana un eksports](export-destinations.md): eksports ir pieejams uzņēmumu kontiem un atsevišķiem klientiem. Dažiem eksportiem ir nepieciešama papildu konfigurācija un kontaktinformācija, kas ir derīga uzņēmuma kontiem.
- [Sistēmas iestatījumi](system.md) un [lietotāju pārvaldība](permissions.md): visi līdzekļi šajā apgabalā uzņēmumu kontiem un atsevišķiem klientiem ir vienādi.

