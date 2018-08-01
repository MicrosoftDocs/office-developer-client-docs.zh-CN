---
title: IOlkApptRebaser
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d67bd395-d324-217d-8ddc-1d48dd724383
description: 定位日历文件夹中的约会的支持。
ms.openlocfilehash: 57ca59121f74c7b64a84282c7493e4aed3179f7a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774361"
---
# <a name="iolkapptrebaser"></a>IOlkApptRebaser

定位日历文件夹中的约会的支持。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|继承：  <br/> |**IUnknown** <br/> |
|头文件：  <br/> |tzmovelib.h  <br/> |
|通过实现：  <br/> |tzmovelib.dll  <br/> |
|调用：  <br/> |MAPI 客户端应用程序  <br/> |
|公开上：  <br/> |Outlook 调整对象  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|**[BeginEnumerateAppointments](iolkapptrebaser-beginenumerateappointments.md)** <br/> |从开始的任务在日历文件夹以查找需要重定基址的约会的约会枚举。  <br/> |
|**[EndEnumerateAppointments](iolkapptrebaser-endenumerateappointments.md)** <br/> |等待要完成的日历文件夹中的约会枚举和返回的约会列表，需要重定基址。  <br/> |
|**[BeginRebaseAppointments](iolkapptrebaser-beginrebaseappointments.md)** <br/> |开始任务的约会定位给定的约会，通常从**EndEnumerateAppointments**获得列表。  <br/> |
|**[EndRebaseAppointments](iolkapptrebaser-endrebaseappointments.md)** <br/> |等待约会重定基址来完成，并检索结果。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [有关重定基址日历以编程方式为夏时制](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

