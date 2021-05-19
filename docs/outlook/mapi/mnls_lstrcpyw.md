---
title: MNLS_lstrcpyW
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a0f92c2d-b5ba-4558-b8a2-484b2db32bec
description: 上次修改时间：2012 年 6 月 18 日
ms.openlocfilehash: 1a1cf0a607dd4b57353eda74f9b14965e110c071
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341725"
---
# <a name="mnls_lstrcpyw"></a>MNLS_lstrcpyW

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将字符串复制到缓冲区。
  
> [!CAUTION]
> 请勿使用。 请考虑改为[使用 StringCchCopy。](https://msdn.microsoft.com/library/ms647527%28VS.85%29.aspx) 
  
```cpp
LPWSTR MNLS_lstrcpyW(
 LPWSTR lpString1,
LPCWSTR lpString2);
```

## <a name="parameters"></a>参数

lpString1
  
> [out]用于接收 lpString2 参数指向的字符串内容的缓冲区。
    
lpString2
  
> [in]要复制的以 null 结尾的字符串。
    
## <a name="return-value"></a>返回值

如果函数成功，则返回值是指向缓冲区的指针。
  
如果函数失败，则返回值为 NULL，lpString1 不能以 null 结束。
  
## <a name="remarks"></a>备注

此函数包装 **lstrcpy** 函数。 有关详细信息，请参阅 [lstrcpy](https://msdn.microsoft.com/library/ms647490%28VS.85%29.aspx)。
  
## <a name="see-also"></a>另请参阅



[lstrcpy](https://msdn.microsoft.com/library/ms647490%28VS.85%29.aspx)

