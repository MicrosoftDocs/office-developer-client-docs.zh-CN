---
title: IOlkApptRebaser
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d67bd395-d324-217d-8ddc-1d48dd724383
description: 支持重设置日历文件夹中的约会的Babas。
ms.openlocfilehash: cf4f7c790a8561f149160c83418a0d5ebd91a455
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410068"
---
# <a name="iolkapptrebaser"></a>IOlkApptRebaser

支持重设置日历文件夹中的约会的Babas。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|继承自：  <br/> |**IUnknown** <br/> |
|标头文件：  <br/> |tzmovelib.h  <br/> |
|实现者：  <br/> |tzmovelib.dll  <br/> |
|调用者：  <br/> |MAPI 客户端应用程序  <br/> |
|在：  <br/> |Outlook重做对象  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|**[BeginEnumerateAppointments](iolkapptrebaser-beginenumerateappointments.md)** <br/> |从开始的任务在日历文件夹以查找需要重定基址的约会的约会枚举。  <br/> |
|**[EndEnumerateAppointments](iolkapptrebaser-endenumerateappointments.md)** <br/> |等待要完成的日历文件夹中的约会枚举和返回的约会列表，需要重定基址。  <br/> |
|**[BeginRebaseAppointments](iolkapptrebaser-beginrebaseappointments.md)** <br/> |在给定约会列表（通常从 **EndEnumerateAppointments** 获取）后，开始为约会重设定底值的任务。  <br/> |
|**[EndRebaseAppointments](iolkapptrebaser-endrebaseappointments.md)** <br/> |等待约会重定基址来完成，并检索结果。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [有关重定基址日历以编程方式为夏时制](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

