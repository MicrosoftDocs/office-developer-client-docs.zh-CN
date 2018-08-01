---
title: UFromSz
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.UFromSz
api_type:
- COM
ms.assetid: 4a67faa2-8c2e-49a7-8c92-690a0a65c8f7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5be5cd7c352201159c0257861c0072b56da65082
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779042"
---
# <a name="ufromsz"></a>UFromSz

  
  
**适用于**： Outlook 
  
小数位数以 null 结尾的字符串转换为无符号整数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
UINT UFromSz(
  LPCSTR lpsz
);
```

## <a name="parameters"></a>参数

 _lpsz_
  
> [in]指向以 null 结尾的字符串，要转换的指针。 _Lpsz_参数不能超过 65536 个字符。 
    
## <a name="return-value"></a>返回值

 **UFromSz**返回无符号的整数。 如果未与至少一个十进制开始字符串，则将返回零。 
  
## <a name="remarks"></a>说明

**UFromSz**函数将停止转换时到达不是小数数字字符串中的第一个字符。 **UFromSz**给定"55"的字符串，例如，返回 55 的整数值。 给定字符串"5a5b"，则函数返回 5 的整数值。 **UFromSz**给定字符串"a5b5"，将返回零。 
  
 对发音差异敏感**UFromSz** 。 支持 Unicode 和 DBCS 格式的字符串。 以字符为单位，不必字节_lpsz_的长度限制。 
  

