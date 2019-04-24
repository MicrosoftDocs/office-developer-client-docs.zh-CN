---
title: IOlkApptRebaserBeginEnumerateAppointments
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8946703a-aaa8-6b3f-aa68-931365db620d
description: 从开始的任务在日历文件夹以查找需要重定基址的约会的约会枚举。
ms.openlocfilehash: cc89b3510f09bb98fd6720cb6d5ab3edeb13eac8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321936"
---
# <a name="iolkapptrebaserbeginenumerateappointments"></a>IOlkApptRebaser::BeginEnumerateAppointments

从开始的任务在日历文件夹以查找需要重定基址的约会的约会枚举。
  
## <a name="quick-info"></a>快速信息

请参阅[IOlkApptRebaser](iolkapptrebaser.md)。
  
```cpp
HRESULT BeginEnumerateAppointments( 
    PFNREBASETASKPROGRESS pfnProgress, 
    void **ppContext);
```

## <a name="parameters"></a>参数

_pfnProgress_
  
> [中]可选。指向用于接收进度的重定基本值任务进度函数的指针。 **PFNREBASETASKPROGRESS** 是在 tzmovelib.h 中定义的。 
    
_ppContext_
  
> [] out所必需。指向返回上下文的指针的指针。此上下文将被传递到[IOlkApptRebaser::EndEnumerateAppointments](iolkapptrebaser-endenumerateappointments.md)。
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>注解

在新线程上执行此任务。
  
## <a name="see-also"></a>另请参阅

- [有关重定基址日历以编程方式为夏时制](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

