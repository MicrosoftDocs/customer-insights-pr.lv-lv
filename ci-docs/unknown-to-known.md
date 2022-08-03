---
title: Personalizējiet savu pieredzi ar datiem par zināmiem un nezināmiem lietotājiem
description: Iekļaujiet informāciju par agrāk nezināmiem lietotājiem, kad zināt viņu identitāti.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: ff99721bef0004bc8cae1ec14ff9df16cbb0682e
ms.sourcegitcommit: ece8ff732490ecd3b3421ab273f331e6fd46a7f7
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/19/2022
ms.locfileid: "9173820"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Personalizējiet savu pieredzi ar datiem par zināmiem un nezināmiem lietotājiem

Klientu datu pārvaldība nav jauns izaicinājums, taču tas kļūst arvien grūtāk, jo lietotāji pārvietojas pa dažādiem digitālo kanālu zīmoliem. Lietotājs, kurš ir zināms (autentificēts) vienā kanālā, kļūst nezināms (neautentificēts) citā kanālā, ja tas nav pieteicies. Bieži problēma ir tā, ka neautentificētiem (nezināmiem) lietotājiem nav kopēja ID. To var izmantot, lai saistītu jēgpilnus profilu atribūtus un ģenerētu vienotus klientu profilus. Customer Insights palīdz atrisināt šo problēmu, uzņemot datus no izsekošanas metodēm jūsu avota sistēmās. Konsolidētie nezināmie un zināmie profili sniedz organizācijām pilnīgu priekšstatu par jaunākajiem profiliem un to vēsturiskajām transakcijām, uzvedību un demogrāfiskajiem datiem. Tas pat iet soli tālāk, nodrošinot identitātes izšķirtspēju, kas ļauj apvienot klientu aktivitātes vairākos kanālos, tostarp jūsu vietnē, pirkumos veikalā, lojalitātes programmās utt.

## <a name="sample-scenario"></a>Scenārija paraugs

Padomāsim par kafijas ķēdi, kurai ir plaša klientu bāze, kas veikalos iegādājas kafiju un pārtiku un pasūta produktus tiešsaistē. Bieži vien, pārlūkojot produktus, tiešsaistes apmeklētāji netiek autentificēti, padarot tos par "nezināmiem lietotājiem". Kafijas ķēdei ir grūti piegādāt personalizētus piedāvājumus un pieredzi, ja lietotāji nav zināmi. No otras puses, klienti var pieteikties savā kontā un kļūt par "zināmiem lietotājiem" uzņēmumam, pievienojoties lojalitātes sistēmai, kas savukārt ļauj personalizētāku pieredzi. Customer Insights var palīdzēt kafijas ķēdei gūt ieskatus par zināmiem un iepriekš nezināmiem lietotājiem.

Izmantojot Customer Insights, uzņēmums var apvienot klientu profilus ar darbību datiem no neautentificētām (nezināmām) sesijām pēc tam, kad lietotājs ir pierakstījies un kļuvis zināms. Kafijas ķēde var pārnest datus no citiem datu avotiem, izmantojot iebūvētus savienotājus Customer Insights, lai sapludinātu identitātes klientiem no dažādiem kanāliem.

## <a name="prerequisites"></a>Priekšnoteikumi

- Tīmekļa dati tiek apkopoti, un tie satur "apmeklētāju ID" visiem apmeklētājiem.
- Tīmekļa dati satur "autentificētus lietotāja ID" pieteikušies apmeklētājiem. Šie ID ir saistīti ar lojalitātes sistēmu.
- Augstvērtīgu notikumu dati, piemēram, "Produkta skats" un "Izrakstīšanās", tiek definēti un iekļauti avota datos kopā ar notikuma laikspiedolu un notikuma ID.

Nākamajā tabulā ir parādīts vienkāršots piemērs tam, kā varētu tikt tverti vērtīgi tīmekļa notikumi.

|Notikuma ID|EventTimeStamp|Lietotāja ID|LojalitātesID|Notikuma_nosaukums|
|--|--|--|--|--|
|1|07-23-2022 10:00:00|abc123|--|Produkta skats|
|2|07-23-2022 10:05:00|abc123|707|Lojalitātes pierakstīšanās|
|3|07-23-2022 10:10:00|abc123|707|Norēķināšanās|
|4|07-23-2022 10:20:00|xyz789|--|Produkta skats|

## <a name="data-ingestion"></a>Datu pieņemšana

Dati par klientiem var būt iegūti no jūsu vietnes kā notikumu dati, un tos var saglabāt jūsu iekšējos vai trešo pušu datu analīzes pakalpojumos. Tīmekļa dati satur zināmus un nezināmus lietotājus, ja tīmekļa vietnei ir autentifikācijas plūsma, kas integrējas ar autentifikācijas pakalpojumu. Piemēram, e-komercijas sistēma, kas pieprasa lietotājiem sniegt pilnīgu informāciju, lai pabeigtu pirkšanas transakciju. Vai lojalitātes sistēma, kurai nepieciešama autentifikācija, lai apstiprinātu derīgu atlīdzības atlaižu saņēmēju.

Notikumu dati mūsu iepriekš minētajā piemērā satur zināmo un nezināmo lietotāju atšķirīgos profila ID. 1. un 4. gadījumā lietotāji nav zināmi, savukārt 2. un 3. gadījumā lietotājs ar ID abc123 reģistrējas lojalitātes programmā.

:::image type="content" source="media/website-data-source.png" alt-text="Datu avoti, tostarp Contoso tīmekļa vietne.":::

Papildinformāciju par pieejamajām datu uzņemšanas opcijām skatiet rakstā [Pārskats par datu avotiem](data-sources.md).

## <a name="data-unification"></a>Datu apvienošana

Nezināmu identitāšu saplūšana ar zināmām identitātēm palīdz iespējot personalizēšanu, pamatojoties uz lietotāju uzvedību, neatkarīgi no viņu profila stāvokļa (zināma vai nezināma). Personalizēts saturs visiem lietotājiem palīdz klientiem ātri piekļūt visatbilstošākajiem produktiem vai pakalpojumiem, kas viņus interesē tajā brīdī.

Tā kā daži no mūsu datos iekļautajiem lietotājiem ir zināmi, mēs varam izmantot Customer Insights, lai apvienotu šos datus ar lietotāja profilu. Papildinformāciju par klientu profilu apvienošanu skatiet rakstā [Datu apvienošanas pārskats](data-unification.md).

1. Atlasiet avota laukus no tīmekļa datu entītijas. Izmantojiet profila datus, kas tiek glabāti jūsu tīmekļa datos, un atlasiet laukus, kas attēlo ID ar demogrāfiskiem datiem.

   :::image type="content" source="media/website-source-fields.png" alt-text="Tīmekļa datu avots avota lauki.":::

1. Pievienojiet kārtulas ierakstu dublikātu sapludināšanai. Tīmekļa datiem izvēlieties visvairāk aizpildītos datus.

1. Konfigurējiet atbilstības kārtulas un nosacījumus. Šajā piemērā norādītie tīmekļa profilu notikumu dati tiks saskaņoti ID ar profiliem no citiem datu avotiem, kas satur klientu informāciju. Iestatiet precīzas atbilstības kārtulas ID kā atsevišķas kārtulas ar katru citu profila entītiju, kurai ir atbilstoša primārā atslēga vai ID atbilstība. Piemērā tīmekļa notikumu profila dati tiek izmantoti kā pēdējā atbilstošā entītija, lai vispirms tiktu apvienoti citi profila dati.
   1. Nepārbaudīšana **Iekļaut visus ierakstus** izveido vienotus profilus zināmiem lietotājiem un ietver viņu atbilstošos nezināmos lietotāju ID. Tas ir noderīgi scenārijos, kad jūs interesē, lai skatītu zināmo lietotāju iepriekšējās uzvedības darbības, kad tās vēl nebija zināmas.
   1. Pārbaudot **Iekļaut visus ierakstus**, nezināmiem lietotājiem tiek izveidoti atsevišķi profila ieraksti. Nezināmi lietotāji iegūst unikālu klienta ID. Nākotnē, kad zināms profils ir saistīts ar tīmekļa notikumu profila datiem, nesen zināmo lietotāja ceļojumu var apskatīt un izmantot personalizēšanai, pamatojoties arī uz pagātnes nezināmiem uzvedības datiem.

:::image type="content" source="media/website-match-rule.png" alt-text="Atbilstības kārtula tīmekļa vietnei datu avots entītijai.":::

## <a name="get-insights"></a>Iegūt ieskatus

Ja nezināmiem un zināmiem lietotājiem tiek izveidoti klientu profili, augstvērtīgus tīmekļa notikumu datus var izmantot kā [darbības](activities.md). Šīs darbības var izmantot, lai gūtu vairāk ieskatu. Piemēram, klienti, kuri apmeklēja vietni pirms sešiem mēnešiem (kad viņi vēl nebija zināmi) vai klienti, kuriem nav lojalitātes ID, nekad nav pabeiguši norēķināšanos.

:::image type="content" source="media/website-known-unknown.png" alt-text="Ekrānuzņēmums, kurā redzama klienta lapa ar zināmiem un nezināmiem klientiem.":::

[Bagātiniet](enrichment-hub.md) savus datus, veidojiet [mērus](measures.md) un izveidojiet [segmentus](segments.md) turpmākai aktivizēšanai.

Piemēram, varat izveidot zināmu lietotāju segmentus, kas apskatīja dažus produktus, bet nekad nepabeidza norēķināšanos.

Papildinformāciju skatiet sadaļā [Segmentu pārskats](segments.md).

## <a name="activate-insights"></a>Ieskatu aktivizēšana

Ir vairāki veidi, kā eksportēt datus un veikt darbības, pamatojoties uz pamatā esošajiem ieskatiem.

Papildinformāciju skatiet rakstā [Pārskats par](export-destinations.md) eksportu.
