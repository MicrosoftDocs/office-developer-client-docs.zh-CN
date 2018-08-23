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
ms.openlocfilehash: 87a470c1c682225eb1deefba9ccc8c12fbdc49c9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569825"
---
# <a name="fbinfromhex"></a>FBinFromHex

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
将十六进制数的字符串表示形式转换为二进制数据。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
BOOL FBinFromHex(
  LPSTR sz,
  LPBYTE pb
);
```

## <a name="parameters"></a>参数

 _sz_
  
> [in]以 null 结尾的 ASCII 字符串要转换的指针。 它不是 Unicode 字符串。 有效字符包括十六进制字符 0-9 和两个大写字母和小写字母字符 A 到 f。
    
 _pb_
  
> [输出]指向返回二进制数。
    
## <a name="return-value"></a>返回值

TRUE 
  
> 该字符串已成功转换为二进制数。 
    
FALSE 
  
> 输入的字符串包含无效的 ASCII 十六进制字符。
    
## <a name="see-also"></a>另请参阅



[ScBinFromHexBounded](scbinfromhexbounded.md)

