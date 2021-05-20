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
  
用于描述错误或警告的 32 位状态值。 
  
```cpp
typedef ULONG SCODE;

```

## <a name="remarks"></a>备注

**SCODE** 数据类型与 [HRESULT](hresult.md)属性数据类型。 
  
**SCODE** 值分为四个字段： 
  
- 单位严重性代码，设置为 0 表示成功，1 表示失败。
    
- 11 位保留字段
    
- 指示负责错误或警告的区域的 4 位设备代码。
    
- 描述导致错误或警告的问题的 16 位错误或警告代码。
    
许多 MAPI 函数和方法都返回定义为 **HRESULT** 数据类型的 **SCODE** 值，就像 OLE 方法和函数一样。 OLE 定义多个宏，这些宏可用于在 **SCODE 和** **HRESULT** 之间转换。
  
> [!NOTE]
> 在 64 位 MAPI 中 **，SCODE** 仍是 32 位值。 
  
有关 MAPI 如何使用 **SCODE** 代码的详细信息数据类型，请参阅 [错误处理](error-handling-in-mapi.md)。 有关 OLE 和 **SCODE** 数据类型，请参阅 *《OLE 程序员参考》。* 
  
## <a name="see-also"></a>另请参阅



[[HRESULT]](hresult.md)


[MAPI 数据类型](mapi-data-types.md)

