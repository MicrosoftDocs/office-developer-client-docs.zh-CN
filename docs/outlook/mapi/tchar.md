---
title: TCHAR
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.TCHAR
api_type:
- COM
ms.assetid: 7a92060b-4c30-4eba-993f-36f5f9231a4b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e7b3774d8dce446f0e87f041f11dac607f464680
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778971"
---
# <a name="tchar"></a>TCHAR

  
  
**适用于**： Outlook 
  
Win32 字符的字符串的可以用来描述 ANSI、 DBCS 或 Unicode 字符串。 ANSI 和 DBCS 平台 TCHAR 定义，如下所示：
  
```cpp
typedef char TCHAR;

```

## <a name="remarks"></a>说明

对于 Unicode 平台，TCHAR 被定义为同义 WCHAR 类型。 
  
MAPI 客户端可以使用 TCHAR 数据类型表示 WCHAR 或 char 类型字符串。 请务必定义符号常量 UNICODE 和需要时限制平台。 MAPI 将解释平台信息和内部到适当的字符串翻译 TCHAR。 MAPI 属性类型，PT_TSTRING，适用于一样 TCHAR 数据类型。 当该平台支持 Unicode 时，PT_TSTRING 类型的属性分配类型 PT_UNICODE 编译时。 当平台不支持 Unicode 时，这些属性分配 PT_STRING8 的类型。
  
有关此功能的详细信息，请参阅[字符集](mapi-character-sets.md)和[列表的属性类型](property-types.md)。 
  
## <a name="see-also"></a>另请参阅



[MAPI 数据类型](mapi-data-types.md)

