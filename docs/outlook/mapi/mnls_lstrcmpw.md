---
title: MNLS_lstrcmpW
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d26c59d7-c839-426f-8693-727fc6bef67e
description: 上次修改时间： 2012 年 6 月 18 日
ms.openlocfilehash: 03b0eb794b07bc56ec6dce4a567d89294b2c908a
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386346"
---
# <a name="mnlslstrcmpw"></a>MNLS_lstrcmpW

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
比较两个 Unicode 字符串。
  
```cpp
int MNLS_lstrcmpW(
  LPCWSTR lpString1,
  LPCWSTR lpString2);
```

## <a name="parameters"></a>参数

 _lpString1_
  
> [in]指向要比较的第一个 Unicode 字符串。
    
 _lpString2_
  
> [in]指向要比较的第二个 Unicode 字符串。
    
## <a name="return-value"></a>返回值

返回到除 CSTR_EQUAL **MNLS_CompareStringW**等效呼叫的描述的值。 
  
## <a name="remarks"></a>说明

 _MNLS_lstrcmpW_通过调用[MNLS_CompareStringW](mnls_comparestringw.md)与 GetUserDefaultLCID，用于标志，0 的区域设置执行比较和 cch1 和 cch2-1。 
  
## <a name="see-also"></a>另请参阅



[GetUserDefaultLCID](https://msdn.microsoft.com/library/dd318135%28VS.85%29.aspx)

