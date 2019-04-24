---
title: IOlkApptRebaser
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d67bd395-d324-217d-8ddc-1d48dd724383
description: 支持 "日历" 文件夹中的重定约会。
ms.openlocfilehash: cf4f7c790a8561f149160c83418a0d5ebd91a455
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321859"
---
# <a name="iolkapptrebaser"></a>IOlkApptRebaser

支持 "日历" 文件夹中的重定约会。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|继承自:  <br/> |**IUnknown** <br/> |
|标头文件：  <br/> |tzmovelib。h  <br/> |
|实现者：  <br/> |tzmovelib。h  <br/> |
|调用者：  <br/> |MAPI 客户端应用程序  <br/> |
|公开于:  <br/> |Outlook 重定对象  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|**[BeginEnumerateAppointments](iolkapptrebaser-beginenumerateappointments.md)** <br/> |从开始的任务在日历文件夹以查找需要重定基址的约会的约会枚举。  <br/> |
|**[EndEnumerateAppointments](iolkapptrebaser-endenumerateappointments.md)** <br/> |等待要完成的日历文件夹中的约会枚举和返回的约会列表，需要重定基址。  <br/> |
|**[BeginRebaseAppointments](iolkapptrebaser-beginrebaseappointments.md)** <br/> |在给定约会列表 (通常从**EndEnumerateAppointments**获取) 的情况下, 开始为约会重定任务。  <br/> |
|**[EndRebaseAppointments](iolkapptrebaser-endrebaseappointments.md)** <br/> |等待约会重定基址来完成，并检索结果。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [有关重定基址日历以编程方式为夏时制](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

