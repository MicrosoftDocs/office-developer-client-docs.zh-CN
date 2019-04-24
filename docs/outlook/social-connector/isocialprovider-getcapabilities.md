---
title: ISocialProviderGetCapabilities
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f40d5405-12e3-475b-b731-d2223ab70c1d
description: 获取描述提供程序功能的字符串。
ms.openlocfilehash: cf3d1418ac0ecbfc3f67bb550a24ec71781f2637
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285761"
---
# <a name="isocialprovidergetcapabilities"></a>ISocialProvider::GetCapabilities

获取描述提供程序功能的字符串。
  
```cpp
HRESULT _stdcall GetCapabilities([out, retval] BSTR* result);
```

## <a name="parameters"></a>参数

_result_
  
> 排除一个代表 Outlook Social Connector (.osc) 提供程序的功能的 XML 字符串。
    
## <a name="remarks"></a>注解

返回的_结果_XML 字符串必须符合 "**功能**" 元素的架构定义 (如在用于 .osc 提供程序扩展性的 XML 架构中定义)。 
  
提供程序必须返回_结果_字符串, 才能使来自 .osc 的后续调用能够正常运行。 
  
## <a name="see-also"></a>另请参阅

- [ISocialProvider : IUnknown](isocialprovideriunknown.md)

