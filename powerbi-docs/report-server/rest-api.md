---
title: "Power BI jelentéskészítő kiszolgáló – kibocsátási megjegyzések"
description: "A REST API szoftveres hozzáférést biztosít Power BI jelentéskészítő kiszolgáló katalógusában lévő objektumokhoz."
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 11/01/2017
ms.author: asaxton
ms.openlocfilehash: 27c4d7c6db43a2332fbef4f444a149ebb3098c43
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/13/2017
---
# <a name="develop-with-the-rest-apis-for-power-bi-report-server"></a>Fejlesztés a Power BI jelentéskészítő kiszolgáló REST API-jaival
A Power BI jelentéskészítő kiszolgáló támogatja a Representational State Transfer (REST) API-kat. A REST API-k HTTP-műveletek (metódusok) készletét támogató szolgáltatásvégpontok, amelyek létrehozási, lekérési, frissítési és törlési jogosultságot biztosítanak a jelentéskészítő kiszolgáló erőforrásaihoz.

A REST API szoftveres hozzáférést biztosít Power BI jelentéskészítő kiszolgáló katalógusában lévő objektumokhoz. Az ilyen objektumok többek között mappák, jelentések, KPI-k, adatforrások, adatkészletek, frissítési tervek és előfizetések lehetnek. A REST API használatával például navigálhat a mappahierarchiában, felderítheti a mappák tartalmát, vagy letöltheti a jelentésdefiníciókat. Emellett létrehozhat, frissíthet és törölhet is objektumokat. Az objektumok kezelésével többek között jelentéseket tölthet fel, frissítési terveket hajthat végre, és mappákat törölhet.

## <a name="components-of-a-rest-api-requestresponse"></a>A REST API-kérések/-válaszok összetevői
A REST API-k kérés-válasz párosai öt összetevőt tartalmaznak:

* A **kérés URI azonosítója**, amely a következőkből áll: `{URI-scheme} :// {URI-host} / {resource-path} ? {query-string}`. Bár a kérés URI azonosítója az üzenet fejlécének részét képezi, itt azért emeljük ki külön, mivel a legtöbb nyelvben és keretrendszerben a kérésüzenettől külön kell beadni.
  
  * URI-séma: A kérés továbbításához használt protokollt jelzi. Például `http` vagy `https`.
  * URI-gazdagép: A REST-szolgáltatásvégpontot futtató kiszolgáló tartománynevét vagy IP-címét adja meg, például `myserver.contoso.com`.
  * Erőforrás elérési útja: Az erőforrást vagy erőforráscsoportot adja meg, és akár a szolgáltatás által az adott erőforrások kiválasztásához használt több szegmens is tartalmazhat. Például a `CatalogItems(01234567-89ab-cdef-0123-456789abcdef)/Properties` használatával lekérhetők a CatalogItem megadott tulajdonságai.
  * Lekérdezési sztring (nem kötelező): További egyszerű paramétereket tartalmaz, például az API-verziót vagy az erőforrások kiválasztási kritériumait.
* HTTP-kérés üzenetfejlécének mezői:
  
  * Egy kötelező [HTTP-metódus](https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html) (más néven művelet vagy ige), amely a kért művelet típusáról tájékoztatja a szolgáltatást. A Reporting Services REST API-jai a DELETE, GET, HEAD, PUT, POST és PATCH metódusokat támogatják.
  * További nem kötelező fejlécmezők, a megadott URI azonosítótól és HTTP-metódustól függően.
* Az URI azonosítót és a HTTP-műveletet támogató, nem kötelező HTTP-**kérésüzenettörzs**-mezők. Például a POST műveletek MIME-kódolású objektumokat tartalmaznak, amelyek összetett paraméterként adhatók be. A POST és PUT műveletek esetében a törzs MIME-kódolásának típusát is meg kell adnia a `Content-type` kérésfejlécben. Egyes szolgáltatások megkövetelik egy adott MIME-típus, például az `application/json` használatát.
* HTTP-**válasz üzenetfejlécének** mezői:
  
  * [HTTP-állapotkód](http://www.w3.org/Protocols/HTTP/HTRESP.html), amely a 2xx sikerkódoktól a 4xx vagy 5xx hibakódokig terjed. Ezek helyett a rendszer visszaadhat a szolgáltatásban definiált állapotkódokat is, ahogy azt az API dokumentációja leírja.
  * A kérésre adott választ támogató további, nem kötelező fejlécmezők, például egy `Content-type` válaszfejléc.
* Nem kötelező HTTP-**válasz üzenettörzsének** mezői:
  
  * A MIME-kódolású válaszobjektumok a HTTP-válasz törzsében térnek vissza, mint például a GET metódusra adott, adatokkal visszatérő válaszok. Az ilyen objektumok általában strukturált formában, például JSON vagy XML formátumban térnek vissza a `Content-type` válaszfejlécben jelzett módon.

## <a name="api-documentation"></a>API-dokumentáció
A modern REST API-khoz modern API-dokumentáció szükséges. A REST API-k az OpenAPI specifikációra (más néven a Swagger-specifikációra) épülnek, és a dokumentáció elérhető a [SwaggerHubon](https://app.swaggerhub.com/apis/microsoft-rs/PBIRS/2.0). Az API dokumentálásán túl a SwaggerHub segítségével egy ügyfélkódtár is felépíthető a választott nyelven (többek között JavaScript, TypeScript, C#, Java, Python és Ruby).

## <a name="testing-api-calls"></a>API-hívások tesztelése
HTTP kérés- és válaszüzenetek teszteléséhez használható eszköz a [Fiddler](http://www.telerik.com/fiddler). A Fiddler egy ingyenes webes hibaelhárító proxy, amely el tudja fogni a REST-kéréseket, így könnyen diagnosztizálhatóak a használatával a HTTP kérés- és válaszüzenetek.

## <a name="next-steps"></a>További lépések
Tekintse át a [SwaggerHubon](https://app.swaggerhub.com/apis/microsoft-rs/PBIRS/2.0) az elérhető API-kat.

A minták a [GitHubon](https://github.com/Microsoft/Reporting-Services) érhetők el. A minták között található egy, a TypeScript, a React és a webpack használatával készült HTML5-alkalmazás, valamint egy PowerShell-példa.

További kérdései vannak? [Kérdezze meg a Power BI közösségét](https://community.powerbi.com/)
