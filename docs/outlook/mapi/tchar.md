---
title: TCHAR
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
api_name:
- MAPI.TCHAR
api_type:
- COM
ms.assetid: 7a92060b-4c30-4eba-993f-36f5f9231a4b
description: 上次修改时间：2011 年 7 月 23 日
localization_priority: Priority
ms.openlocfilehash: 2b04ebe6d05cd72a59fe6d44c9138468fd7ddec1
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28710445"
---
# <a name="tchar"></a>TCHAR

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
可用于描述 ANSI、DBCS 或 Unicode 字符串的 Win32 字符字符串。 对于 ANSI 和 DBCS 平台，TCHAR 定义如下：
  
```cpp
typedef char TCHAR;

```

## <a name="remarks"></a>备注

对于 Unicode 平台，TCHAR 定义为与 WCHAR 类型同义。 
  
MAPI 客户端可以使用 TCHAR 数据类型来表示 WCHAR 或 Char 类型的字符串。 请务必定义符号常量 UNICODE 并在需要时对平台执行限制。 MAPI 将转译平台信息并在内部将 TCHAR 转换为相应的字符串。 MAPI 属性类型 PT_TSTRING 的工作方式与 TCHAR 数据类型的工作方式类似。 当平台支持 Unicode 时，将在编译时向类型 PT_TSTRING 的属性分配类型 PT_UNICODE。 当平台不支持 Unicode 时，将向这些属性分配类型 PT_STRING8。
  
有关此功能的详细信息，请参阅[字符集](mapi-character-sets.md)和[属性类型的列表](property-types.md)。 
  
## <a name="see-also"></a>另请参阅



[MAPI 数据类型](mapi-data-types.md)

