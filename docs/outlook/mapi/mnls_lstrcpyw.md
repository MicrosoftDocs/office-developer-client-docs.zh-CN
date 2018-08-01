---
title: MNLS_lstrcpyW
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a0f92c2d-b5ba-4558-b8a2-484b2db32bec
description: 上次修改时间： 2012 年 6 月 18 日
ms.openlocfilehash: 2e4ae22ace37455c9ccb9d8ff2a7f07a48132234
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776526"
---
# <a name="mnlslstrcpyw"></a>MNLS_lstrcpyW

 
  
**适用于**： Outlook 
  
一个字符串复制到的缓冲区。
  
> [!CAUTION]
> 请勿使用。 考虑使用[StringCchCopy](http://msdn.microsoft.com/en-us/library/ms647527%28VS.85%29.aspx) 。 
  
```cpp
LPWSTR MNLS_lstrcpyW(
 LPWSTR lpString1,
LPCWSTR lpString2);
```

## <a name="parameters"></a>参数

lpString1
  
> [输出]要接收 lpString2 参数指向的字符串的内容缓冲区。
    
lpString2
  
> [in]要复制的 null 结尾的字符串。
    
## <a name="return-value"></a>返回值

如果函数成功，返回值是指向缓冲区的指针。
  
如果函数失败，则返回值为 NULL，lpString1 可能无法在 null 结尾。
  
## <a name="remarks"></a>说明

此函数的换行**lstrcpy**函数。 有关详细信息，请参阅[lstrcpy](http://msdn.microsoft.com/en-us/library/ms647490%28VS.85%29.aspx)。
  
## <a name="see-also"></a>另请参阅



[lstrcpy](http://msdn.microsoft.com/en-us/library/ms647490%28VS.85%29.aspx)

