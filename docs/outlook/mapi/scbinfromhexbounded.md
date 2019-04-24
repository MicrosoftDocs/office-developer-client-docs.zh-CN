---
title: ScBinFromHexBounded
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ScBinFromHexBounded
api_type:
- COM
ms.assetid: edac715c-6edb-4b05-82e5-c08c3c7cb6d4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 813fab28e3e865c9f04f85c854b292ce7229dad5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357496"
---
# <a name="scbinfromhexbounded"></a>ScBinFromHexBounded

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将十六进制数的字符串表示形式的指定部分转换为二进制数。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
SCODE ScBinFromHexBounded(
  LPSTR sz,
  LPBYTE pb,
  ULONG cb
);
```

## <a name="parameters"></a>参数

 _sz_
  
> 实时指向要转换的以 null 结尾的字符串的指针。 有效字符包括十六进制字符0到9以及大写和小写字符 a 到 f。
    
 _pb_
  
> 排除指向返回的二进制数的指针。
    
 _cb_
  
> 实时_pb_参数的大小 (以字节为单位)。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 转换成功。
    
MAPI_E_CALL_FAILED
  
> 遇到无效字符。
    
## <a name="see-also"></a>另请参阅



[FBinFromHex](fbinfromhex.md)

