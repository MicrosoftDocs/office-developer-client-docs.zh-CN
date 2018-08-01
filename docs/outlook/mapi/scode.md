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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6cd9dfe8fabd1ae7a4389550c628fb7ceff09ea8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778696"
---
# <a name="scode"></a>SCODE

**适用于**： Outlook 
  
一个 32 位状态值，用来描述错误或警告。 
  
```cpp
typedef ULONG SCODE;

```

## <a name="remarks"></a>说明

**SCODE**数据类型是[HRESULT](hresult.md)的数据类型相同。 
  
**SCODE**值分为四个字段： 
  
- 一位严重性代码都设置为 0 以指示成功，1，以指示故障。
    
- 11 位保留的字段
    
- 4 位设施代码指示负责错误或警告的区域。
    
- 一个 16 位错误或警告代码，其中介绍了将导致错误或警告的问题。
    
许多 MAPI 函数和方法返回**SCODE**值定义为**HRESULT**数据类型，如执行 OLE 方法和函数。 OLE 定义几个可用于**SCODE**和**HRESULT**之间转换的宏。
  
> [!NOTE]
> 64 位 MAPI 中**SCODE**仍是 32 位值之一。 
  
有关如何 MAPI 使用**SCODE**数据类型的详细信息，请参阅[错误处理](error-handling-in-mapi.md)。 有关 OLE 和**SCODE**数据类型的详细信息，请参阅*OLE 程序员参考*。 
  
## <a name="see-also"></a>另请参阅



[[HRESULT]](hresult.md)


[MAPI 数据类型](mapi-data-types.md)

