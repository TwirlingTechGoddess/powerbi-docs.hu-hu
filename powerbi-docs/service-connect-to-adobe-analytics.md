---
title: "Kapcsolódás az Adobe Analytics eszközhöz a Power BI használatával"
description: "Ha a Power BI használatával kapcsolódik az Adobe Analytics elemzőeszközhöz, a fiókhoz tartozó adatokat egy alkalmazás fogja megjeleníteni egy irányítópult és jelentések formájában."
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
ms.openlocfilehash: 2d4d5e71c87a90ef917ea91dd0b7d178a5c0cbfc
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/13/2017
---
# <a name="connect-to-adobe-analytics-with-power-bi"></a>Kapcsolódás az Adobe Analytics eszközhöz a Power BI használatával
Ha a Power BI-ból kíván kapcsolódni az Adobe Analytics eszközhöz, csatlakozzon az Adobe Analytics Marketing Cloud-fiókjához. Az ekkor megjelenő alkalmazás egy Power BI-irányítópult és -jelentéskészlet segítségével tünteti fel a webhelye forgalmára és felhasználóira vonatkozó elemzéseket. Az adatok naponta egyszer automatikusan frissülnek. Az irányítópultot és a jelentéseket használhatja és megtekintheti, de nem mentheti a változásokat.

Kapcsolódjon az [Adobe Analytics](https://app.powerbi.com/getdata/services/adobe-analytics) eszközhöz, vagy tájékozódjon tovább az [Adobe Analytics és a Power BI integrációjáról](https://powerbi.microsoft.com/integrations/adobe-analytics).

## <a name="how-to-connect"></a>A kapcsolódás menete
[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]

1. Válassza az **Adobe Analytics** \>  **Beolvasás** lehetőséget.
   
   ![](media/service-connect-to-adobe-analytics/adobe.png)
2. A Power BI az Adobe Analytics rendszerében egy adott cég- és jelentésazonosítóhoz (nem pedig a jelentéscsomag nevéhez) csatlakozik. A [paraméterek megkereséséről](#FindingParams) alább olvashat részletesebben.
   
   ![](media/service-connect-to-adobe-analytics/parameters.png)
3. A **Hitelesítési módszer**, beállításánál válassza az **oAuth2** \> **Bejelentkezés** lehetőséget. Amikor a rendszer kéri, adja meg az Adobe Analytics-fiók hitelesítő adatait. 
   
    ![](media/service-connect-to-adobe-analytics/creds.png)
   
    ![](media/service-connect-to-adobe-analytics/adobe_signin.png)
4. Az **Elfogadás** elemre kattintva engedélyezze az Adobe Analytics adataihoz való hozzáférést a Power BI számára.
   
   ![](media/service-connect-to-adobe-analytics/adobe_authorize.png)
5. Jóváhagyás után az importálás automatikusan megkezdődik. 

## <a name="view-the-adobe-analytics-dashboard-and-reports"></a>Az Adobe Analytics irányítópultjának és jelentéseinek megtekintése
[!INCLUDE [powerbi-service-apps-open-app](./includes/powerbi-service-apps-open-app.md)]

      ![Adobe Analytics dashboard](media/service-connect-to-adobe-analytics/dashboard.png)

[!INCLUDE [powerbi-service-apps-open-app](./includes/powerbi-service-apps-what-now.md)]

## <a name="whats-included"></a>Tartalom
A Power BI az Adobe Analytics jelentéskészítő API segítségével a következő táblázatokhoz határoz meg és futtat jelentéseket:

| **Táblázat neve** | **Oszlop adatai** |
| --- | --- |
| Termékek |elements=  "product" (top 25) </br> metrics="cartadditions", "cartremovals", "carts", "cartviews", "checkouts", "revenue", "units" |
| Böngészők |elements= "browser" (top 25)</br>  metrics="bounces", "bouncerate", "visitors", "visits", "uniquevisitors", "totaltimespent", "pageviews" |
| Oldalak |elements= "page" (top 25)</br>  metrics="cartadditions", "cartremovals", "carts", "cartviews", "checkouts", "revenue", "units", "visits", "uniquevisitors", "pageviews", "bounces", "bouncerate", "totaltimespent" |
| JavaScript engedélyezve |elements=  "javascriptenabled”, “browser” (top 25) |
| Mobil operációs rendszer |elements= "mobileos"(top 25)</br> metrics="bounces", "bouncerate", "visitors", "visits", "uniquevisitors", "totaltimespent", "cartadditions", "cartremovals", "checkouts", "revenue", "units", "pageviews" |
| Keresőmotor-kulcsszavak |elements= "searchengine" "searchenginekeyword"</br>  metrics="bounces", "bouncerate", "visitors", "visits", "entries", "uniquevisitors", "totaltimespent", "cartadditions", "cartremovals", "carts", "cartviews", "checkouts", "revenue", "units", "pageviews" |
| Keresőmotor termékekhez |elements= "searchengine", "product"</br>  metrics="bounces", "bouncerate", "visitors", "visits", "entries", "uniquevisitors", "totaltimespent", "cartadditions", "cartremovals", "carts", "cartviews", "checkouts", "revenue", "units", "pageviews" |
| Hivatkozó lapok |elements= "referrer" (top 15), “page" (top 10)</br>  metrics="bounces", "bouncerate", "visitors", "visits", "entries", "uniquevisitors", "totaltimespent", "cartadditions", "cartremovals", "carts", "cartviews", "checkouts", "revenue", "units", "pageviews" |
| Geocountry-oldalak |elements= "geocountry" (Top 20), "page"</br>  metrics="bounces", "bouncerate", "visitors", "visits", "entries", "uniquevisitors", "totaltimespent", "cartadditions", "cartremovals", "carts", "cartviews", "checkouts", "revenue", "units", "pageviews" |
| Geocountry termék |elements= "geocountry" (Top 20), "product"</br> metrics="bounces", "bouncerate", "visitors", "visits", "entries", "uniquevisitors", "totaltimespent", "cartadditions", "cartremovals", "carts", "cartviews", "checkouts", "revenue", "units" |
| Keresés ország és régió szerint |elements= "geocountry" (Top 200)</br>  metrics="bounces", "bouncerate", "visitors", "visits", "entries", "uniquevisitors", "totaltimespent", "cartadditions", "cartremovals", "carts", "cartviews", "checkouts", "revenue", "units" |
| Nyelv |elements= "language", "browser" (Top 25)</br>  metrics="bounces", "bouncerate", "visitors", "visits", "uniquevisitors", "totaltimespent", "pageviews", "cartadditions", "cartremovals", "checkouts", "carts", "cartviews" |
| Keresés keresőmotor szerint |elements= "searchengine" (top 100)</br>  metrics="bounces", "bouncerate", "visitors", "visits", "entries", "uniquevisitors", "totaltimespent", "cartadditions", "cartremovals", "carts", "cartviews", "checkouts", "revenue", "units" |
| Keresés böngésző szerint |elements= "browser" (top 25) |

## <a name="system-requirements"></a>Rendszerkövetelmények
Hozzáférés az [Adobe Analytics eszközhöz](http://www.adobe.com/marketing-cloud/web-analytics.html), az alábbiakban leírt helyes paramétereket is beleértve.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Paraméterek keresése
**Cég**

A Cég érték bejelentkezés után a fiók jobb felső részén látható. Ügyeljen a kis- és nagybetűk, valamint a szóköz használatára. Pontosan úgy kell beírnia, ahogy a fiókban szerepel.

![](media/service-connect-to-adobe-analytics/adobe_companies.png)

**A jelentéscsomag azonosítója**

A jelentéscsomag azonosítója a jelentéscsomaggal együtt jön létre. Az azonosító értékének meghatározásához forduljon a rendszergazdához. Vegye figyelembe, hogy ez nem azonos a jelentéscsomag nevével.

Az Adobe [dokumentációjából](https://marketing.adobe.com/resources/help/en_US/reference/new_report_suite.html):

![](media/service-connect-to-adobe-analytics/reportsuiteid.png)

## <a name="troubleshooting"></a>Hibaelhárítás
Ha a hitelesítő adatok beírása után hiányzó engedélyről szóló hibaüzenetet kap, ellenőrizze a rendszergazdánál, hogy van-e hozzáférése az Adobe Analytics API-hoz. Győződjön meg arról is, hogy a megadott Adobe-azonosító kapcsolódik az Ön (Adobe Analytics-céghez társított) Marketing Cloud cégéhez.

Ha a hibaüzenet azután jelenik meg, hogy sikeresen túljutott a hitelesítő adatok képernyőn, lehetséges hogy a jelentések befejezése túl sokáig tart. Gyakori hibaüzenet *„A jelentések lekérése az Adobe Analytics jelentésből sikertelen volt. Tartalom többek között a &quot;hivatkozó, oldal&quot;, az időtartam körülbelül xx másodperc volt”*. Tekintse át a „Tartalom” szakaszt, és vesse össze az Adobe-példány méretével. Erre az időkorlátra jelenleg nem lehet megoldást találni, de foglalkozunk a lehetőséggel, hogy támogatási frissítéseket nyújtsunk a nagyobb példányok számára, ezért a Power BI csapata várja a visszajelzését a https://ideas.powerbi.com oldalon.

## <a name="next-steps"></a>Következő lépések
* [Alkalmazások a Power BI-ban](service-install-use-apps.md)
* [Adatok beolvasása a Power BI-ban](service-get-data.md)
* További kérdései vannak? [Kérdezze a Power BI-közösséget!](http://community.powerbi.com/)
