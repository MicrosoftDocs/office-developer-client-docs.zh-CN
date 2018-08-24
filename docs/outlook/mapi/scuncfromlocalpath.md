---
title: ScUNCFromLocalPath
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ScUNCFromLocalPath
api_type:
- COM
ms.assetid: cc4abf1a-c08c-4462-9d7c-6af506dc07c9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: faba91d813d27f7ea45e978724ce0d4707803cba
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590104"
---
# <a name="scuncfromlocalpath"></a>ScUNCFromLocalPath

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
查找通用命名约定 (UNC) 路径对应的给定的本地路径。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
SCODE ScUNCFromLocalPath(
  LPSTR szLocal,
  LPSTR szUNC,
  UINT cchUNC
);
```

## <a name="parameters"></a>参数

 _szLocal_
  
> [in]格式中的路径 [_驱动器：_]\[ _路径_] 的文件或目录。
    
 _szUNC_
  
> [输出]格式中的路径\\[_服务器_]\[ _共享_]\[ _路径_] 的相同的文件或目录相同_szLocal_参数。 
    
 _cchUNC_
  
> [in]输出字符串缓冲区的大小。
    
## <a name="return-value"></a>返回值

S_OK
  
> UNC 路径相应已成功找到。
    
MAPI_E_INVALID_PARAMETER
  
> 一个或多个参数均无效。
    
MAPI_E_TOO_BIG
  
>  _szUNC_未足以容纳结果。 
    
S_FALSE
  
> 本地路径已经存在 UNC 字符串。
    
## <a name="see-also"></a>另请参阅



[ScLocalPathFromUNC](sclocalpathfromunc.md)

