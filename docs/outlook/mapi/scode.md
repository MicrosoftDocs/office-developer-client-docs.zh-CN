---
title: SCODE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HRESULT
api_type:
- COM
ms.assetid: 2348cce1-07c3-49ed-ae03-79e477d3c6c2
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4208f51af44055b03c65b51c9b3d94e947dc9b68
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430131"
---
# <a name="scode"></a>SCODE

**适用于**：Outlook 2013 | Outlook 2016 
  
一个用于描述错误或警告的32位状态值。 
  
```cpp
typedef ULONG SCODE;

```

## <a name="remarks"></a>说明

**SCODE**数据类型与[HRESULT](hresult.md)数据类型相同。 
  
**SCODE**值分为四个字段: 
  
- 一个将设置为0以指示成功和1以指示失败的单一位严重性代码。
    
- 11位保留字段
    
- 4位设施代码, 指示负责错误或警告的区域。
    
- 一个16位错误或警告代码, 用于描述导致错误或警告的问题。
    
许多 MAPI 函数和方法返回的**SCODE**值定义为**HRESULT**数据类型, 就像 OLE 方法和函数一样。 OLE 定义了几个可用于在**SCODE**和**HRESULT**之间进行转换的宏。
  
> [!NOTE]
> 在64位 MAPI 中, **SCODE**仍为32位值。 
  
有关 MAPI 如何使用**SCODE**数据类型的详细信息, 请参阅[错误处理](error-handling-in-mapi.md)。 有关 ole 和**SCODE**数据类型的详细信息, 请参阅*OLE 程序员参考*。 
  
## <a name="see-also"></a>另请参阅



[[HRESULT]](hresult.md)


[MAPI 数据类型](mapi-data-types.md)

