---
title: Hisztogramok
description: Hisztogramok
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
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: e5753838365178804dcda4fafd68526ea05aeb73
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2017
---
# <a name="histograms"></a>Hisztogramok
A Power Bi-ban többféle módon is készíthetők hisztogramok. Ez a cikk legegyszerűbbtől kezdve ismerteti ezeket.

## <a name="simple-histograms"></a>Egyszerű hisztogramok
Első lépésként állapítsa meg, hogy melyik lekérdezésben szerepel a hisztogram alapjául szánt mező.  Használja a lekérdezés *Hivatkozás* lehetőségét egy új lekérdezés létrehozásához, amelynek a *MezőNév Hisztogram* nevet adja. Használja az **Átalakítás** menüszalag **Csoportosítás** lehetőségét, és válassza a **sorok száma** összegzést. Ügyeljen rá, hogy az eredmény oszlopának adattípusa szám legyen. Ezeket az adatokat aztán megjelenítheti a jelentések oldalon. Ez a módszer gyors és egyszerűen megvalósítható, de sok adatpont esetén nem működik jól, és nem teszi lehetővé a vizualizációk közötti átlátást.

## <a name="defining-buckets-to-build-a-histogram"></a>Gyűjtők definiálása hisztogram készítéséhez
Állapítsa meg, hogy melyik lekérdezésben szerepel a hisztogram alapjául szánt mező. Használja a lekérdezés *Hivatkozás* lehetőségét egy új lekérdezés létrehozásához, amelynek a *MezőNév* nevet adja.  Most definiálja a gyűjtőket egy szabállyal. Használja az **Oszlop hozzáadása** menüszalag **Egyéni oszlop hozzáadása** lehetőségét, és készítsen egyéni szabályt.

![](media/service-histograms/powerbi-service-histograms_1.png)

Ügyeljen rá, hogy az eredmény oszlopának adattípusa szám legyen. Most már használhatja az **Egyszerű hisztogramok** szakaszban (ennek a cikknek a korábbi részében) leírt csoportosítási technikát a hisztogram előállításához. Ez a módszer több adatpontot kezel, de továbbra sem segít az átlátásban.

## <a name="defining-a-histogram-that-supports-brushing"></a>Átlátást támogató hisztogram definiálása
Átlátásnak nevezik a vizualizációk közötti kapcsolatot, amikor a felhasználó az egyik vizualizáción kijelöl egy adatpontot, és a jelentésoldalon lévő többi vizualizáció kiemeli vagy megszűri a kiemelthez kötődő adatpontokat.  Mivel az adatok kezelése lekérdezési időben történik, relációkat kell létrehozni a táblák között, és pontosan tudni kell, hogy melyik elem tartozik a hisztogrambeli gyűjtőhöz és viszont.

A folyamat első lépéseként használja a hisztogram alapjául szánt mezőt tartalmazó lekérdezés *Hivatkozás* lehetőségét.  Legyen az új lekérdezés neve *Gyűjtők*.  Ebben a példában az eredeti lekérdezés neve legyen *Részletek*.  Most távolítson el minden oszlopot a hisztogram gyűjtőjeként használni kívánt oszlopon kívül.  Most használja a lekérdezésben az oszlop kijelölése után a helyi menüben található *Ismétlődések eltávolítása* funkciót, hogy a megmaradó értékek az oszlop egyedi értékei legyenek. Tizedes törtek esetén előbb használhatja a gyűjtők definiáláshoz kapott javaslatot, hogy a hisztogramhoz kezelhető számú gyűjtő tartozzon.  Most ellenőrizze a lekérdezés előnézetében látható adatokat. Ha üres vagy NULL értékű mezőket lát, akkor azokat javítania kell még a reláció létrehozása előtt. Lásd: "Reláció létrehozása NULL értékű vagy üres mezők esetén". Ez a módszer nehézségeket okozhat, mert az adatok rendezését igényli. A gyűjtők megfelelő rendezéséről a "Rendezési sorrend: kategóriák rendezése a kívánt sorrendbe" című témakör szól. 

> [!NOTE]
> Mielőtt hozzákezd a vizualizációk készítéséhez, érdemes átgondolni a rendezési sorrendet.   
> 
> 

A folyamat következő lépése a *Gyűjtők* és a *Részletek* lekérdezés közötti reláció definiálása a gyűjtők oszlopában.  Válassza a *Relációk kezelése* lehetőséget a *Power BI Desktop* menüszalagján.  Hozzon létre egy relációt amelyben a *Gyűjtők* a bal, a *Részletek* pedig a jobb oldali táblában van, és válassza ki a hisztogramhoz használt mezőt. 

Az utolsó lépés a hisztogram létrehozása. Húzza át a Gyűjtő mezőt a *Gyűjtők* táblából. Távolítsa el az alapértelmezett mezőt a létrejött oszlopdiagramból.  A *Részletek* táblából húzza át a hisztogram mezőjét ugyanarra a vizualizációra. A mezők gyűjtőjében változtassa az alapértelmezett összegzést számlálásra (Count). Az eredmény már a kész hisztogram. Ha újabb vizualizációt, például fatérképet hoz létre a Részletek táblából, akkor jelöljön ki egy adatpontot a fatérképen, és figyelje meg a hisztogram kiemelését és a kijelölt adatpontnak a teljes adatkészlet trendjéhez viszonyított hisztogramját.
