---
title: FBinFromHex
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FBinFromHex
api_type:
- COM
ms.assetid: 47e6c576-bd99-4410-8e41-7dd3159b23b7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 55c7deec9d29ae22a07b2f5ccd1c832d56782c03
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414933"
---
# <a name="fbinfromhex"></a>FBinFromHex

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将十六进制数的字符串表示形式转换为二进制数据。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
BOOL FBinFromHex(
  LPSTR sz,
  LPBYTE pb
);
```

## <a name="parameters"></a>参数

 _sz_
  
> [in]指向要转换的以 null 结尾的 ASCII 字符串的指针。 这不是 Unicode 字符串。 有效字符包括从 0 到 9 的十六进制字符以及大写和小写字符 A 到 F。
    
 _pb_
  
> [out]指向返回的二进制数的指针。
    
## <a name="return-value"></a>返回值

TRUE 
  
> 字符串已成功转换为二进制数。 
    
FALSE 
  
> 输入字符串包含无效的 ASCII 十六进制字符。
    
## <a name="see-also"></a>另请参阅



[ScBinFromHexBounded](scbinfromhexbounded.md)

