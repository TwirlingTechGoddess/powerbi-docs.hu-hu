---
title: "Csatlakozás Amazon Redshift-adatbázishoz a Power BI Desktopban"
description: "Könnyedén csatlakozhat Amazon Redshift-adatbázisokhoz, és használhatja a bennük tárolt adatokat a Power BI Desktopban"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 1321a4d9c7022de95135f3dbbe33a1cf8d80b38f
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-amazon-redshift-in-power-bi-desktop"></a>Csatlakozás Amazon Redshifthez a Power BI Desktopban
A **Power BI Desktopban** csatlakozhat egy **Amazon Redshift**-adatbázishoz, és úgy használhatja az alapul szolgáló adatokat, mint a Power BI Desktop bármely más adatforrását.

## <a name="connect-to-an-amazon-redshift-database"></a>Csatlakozás egy Amazon Redshift-adatbázishoz
Ha csatlakozni szeretne egy **Amazon Redshift**-adatbázishoz, válassza a Power BI Desktop **Kezdőlap** menüszalagján a **Lekérdezés** lehetőséget. Válassza a bal oldali kategóriák közül az **Adatbázis** elemet, és egyéb lehetőségek mellett az **Amazon Redshift** is megjelenik.

![](media/desktop-connect-redshift/connect_redshift_3.png)

A megjelenő **Amazon Redshift** ablakban írja vagy illessze be az **Amazon Redshift**-kiszolgáló és -adatbázis nevét a mezőbe. A *Kiszolgáló* mezőben a felhasználók meghatározhatnak egy portot a következő formátumban: *ServerURL:Port*

![](media/desktop-connect-redshift/connect_redshift_4.png)

Ha a rendszer kéri, adja meg a felhasználónevét és a jelszavát.

![](media/desktop-connect-redshift/connect_redshift_5.png)

Ha sikeresen csatlakozott, megjelenik a **Kezelő** ablaka, és megjeleníti a kiszolgálón elérhető adatokat. Ezek közül kiválaszthat egy vagy több importálni kívánt elemet, és használhatja őket a **Power BI Desktopban**.

![](media/desktop-connect-redshift/connect_redshift_6.png)

Ha kiválasztott valamit a **Kezelő** ablakban, **betöltheti** vagy **szerkesztheti** az adatokat.

* Ha úgy dönt, hogy **betölti** az adatokat, a rendszer rákérdez, hogy az *Importálás* vagy a *DirectQuery* üzemmódot szeretné-e használni. További információért tekintse meg ezt a [cikket, amely a DirectQuery használatát ismerteti](desktop-use-directquery.md).
* Ha a **Szerkesztés** mellett dönt, megjelenik a **Lekérdezésszerkesztő**, ahol sokféle módon átalakíthatja és szűrheti az adatokat, és a műveletek némelyike magára az alapul szolgáló **Amazon Redshift**-adatbázisra is hatással van (ha ez támogatott).

## <a name="next-steps"></a>Következő lépések
A Power BI Desktop használatával számos adatforráshoz csatlakozhat. Az adatforrásokkal kapcsolatos információkért lásd az alábbi forrásanyagokat:

* [Első lépések a Power BI Desktopban](desktop-getting-started.md)
* [Adatforrások a Power BI Desktopban](desktop-data-sources.md)
* [Adatok formázása és kombinálása a Power BI Desktoppal](desktop-shape-and-combine-data.md)
* [Kapcsolódás az Excelhez a Power BI Desktopban](desktop-connect-excel.md)   
* [Adatok közvetlen bevitele a Power BI Desktopba](desktop-enter-data-directly-into-desktop.md)   
