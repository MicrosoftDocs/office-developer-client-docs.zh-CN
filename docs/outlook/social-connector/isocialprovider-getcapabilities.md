---
title: ISocialProviderGetCapabilities
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f40d5405-12e3-475b-b731-d2223ab70c1d
description: 获取一个描述提供程序功能的字符串。
ms.openlocfilehash: cf3d1418ac0ecbfc3f67bb550a24ec71781f2637
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408101"
---
# <a name="isocialprovidergetcapabilities"></a>ISocialProvider::GetCapabilities

获取一个描述提供程序功能的字符串。
  
```cpp
HRESULT _stdcall GetCapabilities([out, retval] BSTR* result);
```

## <a name="parameters"></a>参数

_result_
  
> [out]一个 XML 字符串，表示 OSC Outlook (连接器) 的功能。
    
## <a name="remarks"></a>备注

返回  _的结果_ XML 字符串必须符合 **capabilities** 元素的架构定义，如 OSC 提供程序扩展性 XML 架构中的定义。 
  
提供程序必须  _返回结果字符串_ ，以使 OSC 对提供程序的后续调用能够正常运行。 
  
## <a name="see-also"></a>另请参阅

- [ISocialProvider : IUnknown](isocialprovideriunknown.md)

