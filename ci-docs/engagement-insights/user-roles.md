---
title: Lomas un atļaujas
description: Darbvietas dalībniekiem pieejamo lomu un atļauju pārskats.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ccc6a1b87b4cc28701e276b6e35432356e7647c4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227548"
---
# <a name="roles-and-permissions"></a>Lomas un atļaujas

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Darbvieta ir notikumu un atskaišu glabāšanas un pārvaldīšanas vieta. Papildinformāciju skatiet rakstā [Darbvietas izveide un dalībnieku pievienošana ](create-workspace.md). 

Darbvietā var būt iekļautas šādas lomas un atļaujas:

- *Dalībnieku* lomas ir lietotāji, kas var piekļūt darbvietai. Jūsu darbvietai varat piešķirt dalībniekus un definēt to lomas un atļaujas. 
- *Administratora* lomas pārvalda darbvietas un vides, konfigurējot ieskatus par piesaistīšanu citiem lietotājiem. 
- *Līdzdalībnieku* lomas ir pielāgotas analītiķiem, kuriem nav nepieciešams konfigurēt iesaistes ieskatus, bet vēlas izveidot savas atskaites, piltuves vai segmentus.

## <a name="permissions"></a>Atļaujas
  
Tālāk sniegtajā tabulā ir identificētas katras lomas atļaujas. 

| Atļauja | Vides administrators | Darbvietas administrators | Vides līdzstrādnieks | Darbvietas līdzstrādnieks | 
|--|--|--|--|--|
| Izveidot vides (izveidotājs automātiski kļūst par vides administratoru) | X* | X* | X* | X* |  
| Konfigurēt vidi (vides dalībnieki, dzēst vidi) | X |  |  |  |  
| Izveidot darbvietas | X |  |  |  |  
| Konfigurēt darbvietas (darbvietas dalībnieki, dzēst darbvietu) | X | X |  |  |  
| Notikumu un precizētu notikumu konfigurēšana | X | X | |  |  
| Darbvietas notikumu un precizētu notikumu skatīšana | X | X | |  |  
| Darbvietas resursu (atskaišu, segmentu un rādītāju) skatīšana| X | X | X | X |  
| Pielāgotu atskaišu un piltuvju izveidošana | X | X | X | X |  
| Pamata metriku un dimensiju izveide| X | X |  |  |  
| Izveidot segmentus| X | X | X | X |  

*Var izveidot izmēģinājumversijas tikai priekšskatījumā. 

## <a name="add-members"></a>Pievienot dalībniekus

Dalībniekus var pievienot un noņemt no darbvietām un vidēm. Papildinformāciju skatiet sadaļā [Vides un darbvietas](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
