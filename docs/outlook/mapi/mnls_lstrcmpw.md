---
title: MNLS_lstrcmpW
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d26c59d7-c839-426f-8693-727fc6bef67e
description: 上次修改时间：2012 年 6 月 18 日
ms.openlocfilehash: 03b0eb794b07bc56ec6dce4a567d89294b2c908a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356838"
---
# <a name="mnls_lstrcmpw"></a>MNLS_lstrcmpW

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
比较两个 Unicode 字符串。
  
```cpp
int MNLS_lstrcmpW(
  LPCWSTR lpString1,
  LPCWSTR lpString2);
```

## <a name="parameters"></a>参数

 _lpString1_
  
> [in]指向要比较的第一个 Unicode 字符串的指针。
    
 _lpString2_
  
> [in]指向要比较的第二个 Unicode 字符串的指针。
    
## <a name="return-value"></a>返回值

返回描述的等效调用的值，MNLS_CompareStringW，CSTR_EQUAL。  
  
## <a name="remarks"></a>备注

 _MNLS_lstrcmpW_ 调用 MNLS_CompareStringW GetUserDefaultLCID、0（用于标志）和 -1（对于 cch1 和 cch2）区域设置执行比较。 [](mnls_comparestringw.md) 
  
## <a name="see-also"></a>另请参阅



[GetUserDefaultLCID](https://msdn.microsoft.com/library/dd318135%28VS.85%29.aspx)

