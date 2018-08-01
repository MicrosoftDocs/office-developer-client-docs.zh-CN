---
title: ISocialProviderGetCapabilities
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f40d5405-12e3-475b-b731-d2223ab70c1d
description: 获取一个字符串，描述提供程序功能。
ms.openlocfilehash: 54e28f22f2dc8fdbe19821d8188087b78c327518
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779221"
---
# <a name="isocialprovidergetcapabilities"></a>ISocialProvider::GetCapabilities

获取一个字符串，描述提供程序功能。
  
```cpp
HRESULT _stdcall GetCapabilities([out, retval] BSTR* result);
```

## <a name="parameters"></a>参数

_result_
  
> [输出]一个 XML 字符串值，该值代表 Outlook Social Connector (OSC) 提供程序的功能。
    
## <a name="remarks"></a>说明

返回的_结果_XML 字符串必须符合**capabilities**元素中，架构定义中的 OSC 提供程序扩展性的 XML 架构定义。 
  
提供程序必须返回_结果_字符串要启用对后续调用从 OSC 提供程序才能正常运行。 
  
## <a name="see-also"></a>另请参阅

- [ISocialProvider : IUnknown](isocialprovideriunknown.md)

