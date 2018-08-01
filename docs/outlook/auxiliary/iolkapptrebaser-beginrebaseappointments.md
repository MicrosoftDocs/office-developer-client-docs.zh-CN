---
title: IOlkApptRebaserBeginRebaseAppointments
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ed50422e-9edf-4b73-1789-340b70532621
description: 开始约会重定基址出现的约会，通常从IOlkApptRebaser::EndEnumerateAppointments获得一系列的任务。
ms.openlocfilehash: 2becb305eebe448e2adecf91c2a111f86d97fe50
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774373"
---
# <a name="iolkapptrebaserbeginrebaseappointments"></a>IOlkApptRebaser::BeginRebaseAppointments

开始约会重定基址出现的约会，通常从[IOlkApptRebaser::EndEnumerateAppointments](iolkapptrebaser-endenumerateappointments.md)获得一系列的任务。
  
## <a name="quick-info"></a>快速信息

请参阅[IOlkApptRebaser](iolkapptrebaser.md)。
  
```cpp
HRESULT BeginRebaseAppointments( 
    const SRowSet *pRows, 
    PFNREBASETASKPROGRESS pfnProgress, 
    PFNREBASETASKCOMPLETE pfnComplete, 
    void **ppContext);
```

## <a name="parameters"></a>参数

_pRows_
  
> [中]所必需。指向描述需要重定基址的约会的[SRowSet](http://msdn.microsoft.com/library/7e3761be-afd6-46cb-9a08-25e9016c1241%28Office.15%29.aspx)结构的指针。这种结构通常从[IOlkApptRebaser::EndEnumerateAppointments](iolkapptrebaser-endenumerateappointments.md)到以前的呼叫。
    
_pfnProgress_
  
> [中]可选。指向用于接收进度的重定基本值任务进度函数的指针。 **PFNREBASETASKPROGRESS** 是在 tzmovelib.h 中定义的。 
    
_pfnComplete_
  
> [] out可选。指向用于接收通知的重定基本值完成的重定基本值任务完成函数的指针。 **PFNREBASETASKCOMPLETE** 是在 tzmovelib.h 中定义的。 
    
_ppContext_
  
> [] out所必需。指向返回上下文的指针的指针。通常会将此上下文传递给[IOlkApptRebaser::EndRebaseAppointments](iolkapptrebaser-endrebaseappointments.md)。
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>注释

在新线程上执行此任务。
  
## <a name="see-also"></a>另请参阅

- [有关重定基址日历以编程方式为夏时制](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

