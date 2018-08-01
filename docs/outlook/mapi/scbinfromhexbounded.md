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
ms.openlocfilehash: a00a9b2200f76dfd600f72bf387467b5792599c6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778676"
---
# <a name="scbinfromhexbounded"></a>ScBinFromHexBounded

  
  
**适用于**： Outlook 
  
指定的部分的字符串表示形式的十六进制数转换为二进制数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
SCODE ScBinFromHexBounded(
  LPSTR sz,
  LPBYTE pb,
  ULONG cb
);
```

## <a name="parameters"></a>参数

 _sz_
  
> [in]指向以 null 结尾的字符串，要转换的指针。 有效字符包括十六进制字符 0-9 和两个大写字母和小写字母字符 a 到 f。
    
 _pb_
  
> [输出]指向返回二进制数。
    
 _cb_
  
> [in]大小 （以字节为单位的_pb_参数）。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 转换成功。
    
MAPI_E_CALL_FAILED
  
> 遇到了无效字符。
    
## <a name="see-also"></a>另请参阅



[FBinFromHex](fbinfromhex.md)

