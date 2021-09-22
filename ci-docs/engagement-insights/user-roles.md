---
title: Lomas un atļaujas
description: Darbvietas dalībniekiem pieejamo lomu un atļauju pārskats.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036702"
---
# <a name="roles-and-permissions"></a>Lomas un atļaujas

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Darbvieta ir notikumu un atskaišu glabāšanas un pārvaldīšanas veids. Dalībnieks ir lietotājs, kas var piekļūt darbvietai. Jūsu darbvietai varat piešķirt dalībniekus un definēt to lomas un atļaujas. Administratora lomas pārvalda darbvietas un vides, konfigurējot ieskatus par piesaistīšanu citiem lietotājiem. Līdzdalībnieku lomas ir pielāgotas analītiķiem, kuriem nav nepieciešams konfigurēt iesaistes ieskatus, bet vēlas izveidot savas atskaites, piltuves vai segmentus.

## <a name="permissions"></a>Atļaujas
  
Tālāk sniegtā diagramma identificē katras lomas atļaujas. 

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
