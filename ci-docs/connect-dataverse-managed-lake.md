---
title: Savienojuma izveide ar datiem Microsoft Dataverse pārvaldītā datu ezerā
description: Datu importēšana no Microsoft Dataverse pārvaldītā datu ezera.
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609804"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Savienojuma izveide ar datiem Microsoft Dataverse pārvaldītā datu ezerā

Microsoft Dataverse lietotāji var ātri izveidot savienojumu ar analītiskām entītijām pārvaldītā ezerā Microsoft Dataverse. Tikai vienas vides datu avots var vienlaikus izmantot to pašu Dataverse pārvaldīto ezeru.

> [!NOTE]
> Jums ir jābūt organizācijas administratoram, Dataverse lai turpinātu un skatītu pārvaldītajā ezerā pieejamo entītiju sarakstu.

## <a name="prerequisites"></a>Priekšnoteikumi

- Dati, kas tiek glabāti tiešsaistes pakalpojumos, piemēram, Azure Data Lake Storage, var tikt glabāti citā atrašanās vietā, nevis tajā, kur dati tiek apstrādāti vai glabāti programmā Dynamics 365 Customer Insights.Importējot vai izveidojot savienojumu ar datiem, kas tiek glabāti tiešsaistes pakalpojumos, jūs piekrītat, ka datus var pārsūtīt uz un uzglabāt kopā ar Dynamics 365 Customer Insights. [Uzziniet vairāk Microsoft drošības kontroles centrā](https://www.microsoft.com/trust-center).

- Ir redzamas tikai Dataverse tās entītijas, kurām [ir iespējota izmaiņu izsekošana](/power-platform/admin/enable-change-tracking-control-data-synchronization). Šīs entītijas var eksportēt uz pārvaldīto Dataverse datu ezeru un izmantot programmā Customer Insights. Standarta tabulās Dataverse izmaiņu izsekošana ir iespējota pēc noklusējuma. Jums ir jāieslēdz izmaiņu izsekošana pielāgotām tabulām. Lai pārbaudītu, vai tabula ir iespējota Dataverse izmaiņu izsekošanai, dodieties uz [Power Apps](https://make.powerapps.com) > **Datu** > **tabulas**. Atrodiet sev interesējošo tabulu un atlasiet to. Dodieties uz **Papildu opciju** > **Iestatījumi** un pārskatiet **iestatījumu Izmaiņu reģistrēšana**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Savienojuma izveide ar Dataverse pārvaldīto datu ezeru

1. Dodieties uz **Dati** > **Datu avoti**.

1. Atlasiet **Pievienot datu avotu**.

1. Atlasiet **Microsoft Dataverse**.

1. **Ievadiet datu avots nosaukumu** un neobligātu **aprakstu**.

1. Norādiet **Servera adresi** Dataverse organizācijai un atlasiet **Pieteikties**.

1. Atlasiet tabulas, kuras vēlaties uzņemt kā entītijas programmā Customer Insights no pieejamā saraksta.

   > [!NOTE]
   > Ja dažas tabulas jau ir atlasītas, tās var izmantot citas Dynamics 365 lietojumprogrammas (piemēram, Dynamics 365 Sales Insights vai Customer Service Insights). Atlasi nevar mainīt. Šīs tabulas būs pieejamas kā entītijas, tiklīdz datu avots saraksts.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialoglodziņš, kurā redzams Dataverse vides entītiju saraksts.":::

1. Saglabājiet savu atlasi, lai sāktu atlasīto tabulu sinhronizēšanu no Dataverse. Tikko izveidotais savienojums ir atrodams lapā **Datu avoti**. Tā tiks ievietota rindā atsvaidzināšanai un rādīs entītiju skaitu kā 0, līdz visas atlasītās tabulas tiks sinhronizētas.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Datu ielāde var aizņemt laiku. Pēc veiksmīgas atsvaidzināšanas pieņemtos datus var pārskatīt lapā [**Entītijas**](entities.md).

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Dataverse pārvaldītā datu ezera datu avota rediģēšana

Entītijas atlasi var rediģēt tikai pēc datu avota izveides. Piemēram, ja Dataverse tika pievienotas papildu entītijas un jūs vēlaties importēt arī tās.
Lai izveidotu savienojumu ar citu Dataverse datu ezeru, [izveidojiet jaunu datu avotu](#connect-to-a-dataverse-managed-lake).

1. Dodieties uz **Dati** > **Datu avoti**.

1. Blakus datu avots, kuru vēlaties atjaunināt, atlasiet **Rediģēt**.

1. Atlasiet papildu entītijas no pieejamā entītiju saraksta.

1. Noklikšķiniet uz **Saglabāt**, lai lietotu izmaiņas un atgrieztos **lapā Datu avoti**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>Bieži sastopami norīšanas kļūdu vai bojātu datu iemesli

Šādi ievadītie dati pārbauda, vai tiek rādīti bojāti ieraksti:

- Lauka vērtība neatbilst tā kolonnas datu tipam.
- Laukos ir rakstzīmes, kas liek kolonnai neatbilst gaidītajai shēmai. Piemēram: nepareizi formatēti piedāvājumi, nebeidzami piedāvājumi vai jaunas rindas rakstzīmes.
- Ja ir kolonnas datetime/date/datetimeoffset, to formāts ir jānorāda modelī, ja tas neatbilst standarta ISO formātam.

### <a name="schema-or-data-type-mismatch"></a>Shēmas vai datu tipa neatbilstība

Ja dati neatbilst shēmai, ieraksti tiek klasificēti kā bojāti. Izlabojiet vai nu avota datus, vai shēmu un atkārtoti uzņemiet datus.

### <a name="datetime-fields-in-the-wrong-format"></a>Datuma laika lauki nepareizā formātā

Entītijas datuma laika lauki nav ISO vai en-US formātā. Customer Insights noklusējuma datuma laika formāts ir en-US formāts. Visiem entītijas datuma laika laukiem jābūt vienā formātā. Customer Insights atbalsta citus formātus ar nosacījumu, ka modeļa vai manifest.json avota vai entītijas līmenī tiek veidotas anotācijas vai iezīmes. Piemēram:

**Modelis.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  Manifest.json gadījumā datuma laika formātu var norādīt entītijas līmenī vai atribūtu līmenī. Entītijas līmenī izmantojiet "exhibitsTraits" entītijā *.manifest.cdm.json, lai definētu datu laika formātu. Atribūtu līmenī atribūta atribūtā izmantojiet "appliedTraits" entityname.cdm.json.

**Manifest.json entītijas līmenī**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json atribūtu līmenī**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
