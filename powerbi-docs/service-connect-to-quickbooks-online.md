---
title: "Csatlakozás a QuickBooks Online-hoz a Power BI használatával"
description: QuickBooks Online a Power BI-hoz
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: def174cb86b701f628e4637d3a9933a42c5a5740
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-quickbooks-online-with-power-bi"></a>Csatlakozás a QuickBooks Online-hoz a Power BI használatával
Amikor Power BI-ból csatlakozik a QuickBooks Online-adatokhoz, azonnal megjelenik egy Power BI-irányítópult és néhány Power BI-jelentés, amelyek alapján pénzforgalmával, jövedelmezőségével, ügyfeleivel és sok más területtel kapcsolatban összefüggéseket tárhat fel. Az irányítópultot és a jelentéseket a megjelenített formában is használhatja, illetve igényei szerint át is alakíthatja azokat, hogy azokat az információkat emeljék ki, melyek az Ön számára a legfontosabbak. Az adatokat naponta egyszer automatikusan frissíti a rendszer.

Kapcsolódjon a Power BI-hoz készült [QuickBooks Online-tartalomcsomaghoz](https://dxt.powerbi.com/getdata/services/quickbooks-online).

>[!NOTE]
>A QuickBooks Online adatok Power BI-ba történő importálásához, QuickBooks Online-fiókjában rendszergazdának kell lennie, és rendszergazdai hitelesítő adataival kell bejelentkeznie.

## <a name="how-to-connect"></a>A csatlakozás menete
1. Kattintson az **Adatok lekérése** elemre a bal oldalon lévő navigációs ablaktábla alján.
   
   ![](media/service-connect-to-quickbooks-online/pbi_getdata.png) 
2. A **Szolgáltatások** mezőben kattintson a **Beolvasás** lehetőségre.
   
   ![](media/service-connect-to-quickbooks-online/pbi_getservices.png) 
3. Válassza ki **QuickBooks Online**, majd kattintson a **Letöltés most** lehetőségre.
   
   ![](media/service-connect-to-quickbooks-online/qbo.png)
4. Hitelesítési módszerként válassza az **oAuth2** eljárást, majd kattintson a **Bejelentkezés** lehetőségre. 
5. Amikor a rendszer kéri, adja meg QuickBooks Online hitelesítő adatait, majd haladjon végig a hitelesítési folyamaton. Ha böngészőjében már bejelentkezett a QuickBooks Online-ba, a rendszer nem feltétlenül fogja kérni hitelesítő adatait.
   >[!NOTE]
   >A QuickBooks Online-fiókjába rendszergazdai hitelesítő adatokkal kell bejelentkeznie.
6. A következő képernyőn válassza ki azt a céget, amelyet csatlakoztatni szeretne a Power BI-hoz.
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_almost.png)
7. Az importálási folyamat elindításához a következő képernyőn kattintson az **Authorize** (Engedélyezés) elemre. Ez a vállalati adatok méretétől függően néhány percet is igénybe vehet. 
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_authorizesm.png)
   
   Miután a Power BI importálta az adatokat, a bal oldali navigációs ablaktáblán megjelenik egy új irányítópult, egy új jelentés és egy új adatkészlet. Az új elemeket sárga csillag \* jelöli.
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_leftnavnew.png)
8. Válassza ki a QuickBooks Online irányítópultot. Ez a Power BI által automatikusan létrehozott irányítópult az importált adatok megjelenítéséhez. Az irányítópultot módosíthatja, hogy az igényei szerint jelenítse meg az adatokat. 
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_dash.png)

**Hogyan tovább?**

* [Tegyen fel egy kérdést a Q&A mezőben](service-q-and-a.md), amely az irányítópult tetején található
* [Módosítsa a csempéket](service-dashboard-edit-tile.md) az irányítópulton.
* [Kattintson az egyik csempére](service-dashboard-tiles.md) az alapjául szolgáló jelentés megnyitásához.
* Az adathalmaz naponta frissül, de módosíthatja is a frissítési ütemezést, vagy igény szerint frissíthet bármikor, a **Frissítés** lehetőségre kattintva

## <a name="troubleshooting"></a>Hibaelhárítás
**„Hoppá! Hiba történt.”**

Ha az **Authorize** (Engedélyezés) választása után ezt az üzenetet kapja:

„Hoppá! Hiba történt.” Zárja be ezt az ablakot, és próbálkozzon újra.

Az alkalmazásra már feliratkozott a cég egy másik felhasználója. Az előfizetés módosításához írjon a [rendszergazda e-mail-címe] címre.”

![](media/service-connect-to-quickbooks-online/pbi_qbo_oopssm.png)

... Ez azt jelenti, hogy a cég egy másik rendszergazdája már csatlakozott a vállalati adatokhoz a Power BI-jal. Kérje meg azt a rendszergazdát, hogy ossza meg Önnel az irányítópultot. Jelenleg csak egy rendszergazdai jogú felhasználó csatlakoztathat egy adott QuickBooks Online céges adatkészletet a Power BI-hoz. Ha a Power BI létrehozta az irányítópultot, a rendszergazda megoszthatja az ugyanazon a Power BI bérlőn található munkatársakkal.

**„Az alkalmazásban nincs beállítva az Ön országából induló kapcsolatok engedélyezése"**

A Power BI jelenleg csak a QuickBooks Online egyesült államokbeli kiadásait támogatja. 

![](media/service-connect-to-quickbooks-online/pbi_qbo_countrynotsupported.png)

## <a name="next-steps"></a>Következő lépések
[Power BI ‒ első lépések](service-get-started.md)

[Power BI – alapfogalmak](service-basic-concepts.md)
