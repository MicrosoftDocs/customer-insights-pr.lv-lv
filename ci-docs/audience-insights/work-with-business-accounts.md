---
title: Darba sākšana ar uzņēmuma uzņēmumiem kā primārā mērķa auditorija
description: Darba sākšana ar uzņēmuma uzņēmumiem kā primārā mērķa auditorija programmā Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: fb943a91154e913c85c40fbf6077c171e9240ac5
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977930"
---
# <a name="work-with-business-accounts-in-audience-insights"></a>Darbs ar biznesa uzņēmumiem auditorijas ieskatos

Izmantojot auditorijas ieskatu iespējas programmā Dynamics 365 Customer Insights, varat konfigurēt vidi dažādām primārajām mērķa auditorijām: atsevišķiem klientiem (B2C) un uzņēmuma kontiem (B2B). B2C scenārijos dati tiek centrēti uz atsevišķiem indivīdiem. B2B vajadzībām primārā mērķa auditorija ir uzņēmumi - organizācijas vai uzņēmumi - un kontaktpersonas. Šis raksts palīdz sākt darbu ar uzņēmumu kontu vidi. Atkarībā no vides jomas tajā ir uzskaitītas atšķirības auditorijas ieskatos līdzekļu apgabalos. Lai iegūtu papildinformāciju par atšķirībām, pārskatiet līdzekļu apgabalu dokumentus. 

## <a name="create-an-environment-for-business-accounts"></a>Vides izveide uzņēmuma kontiem

Administratori var [izveidot vidi esošā organizācijā](create-environment.md). Jaunas vides izveides procesā notiek darbība, kurā administratoriem tiek lūgts izmantot vides primāro mērķa auditoriju. Ja pēc licences iegādes tā ir auditorijas ieskatu sākotnējā iestatīšana, vadītā pieredze palīdz izveidot pirmo vidi.

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

