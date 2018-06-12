---
title: ScLocalPathFromUNC
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ScLocalPathFromUNC
api_type:
- COM
ms.assetid: ef5eb5c6-251e-4a3a-8855-7c28804a29ab
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: e94692ac4eb401109fcb522e6224c8748bef37f7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778702"
---
# <a name="sclocalpathfromunc"></a>ScLocalPathFromUNC

  
  
**适用于**： Outlook 
  
查找本地路径对应的给定的通用命名约定 (UNC) 路径。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
SCODE ScLocalPathFromUNC(
  LPSTR szUNC,
  LPSTR szLocal,
  UINT cchLocal
);
```

## <a name="parameters"></a>参数

 _szUNC_
  
> [in]格式中的路径\\[_服务器_]\[ _共享_]\[ _路径_] 的文件或目录。
    
 _szLocal_
  
> [输出]格式中的路径 [_驱动器：_]\[ _路径_] 的相同的文件或目录相同_szUNC_参数。 
    
 _cchLocal_
  
> [in]输出字符串缓冲区的大小。
    
## <a name="return-value"></a>返回值

S_OK
  
> 本地路径已成功找到。
    
MAPI_E_TOO_BIG
  
>  _szLocal_未足以容纳结果。 
    
S_FALSE
  
> UNC 字符串已本地路径。
    
MAPI_E_NOT_FOUND
  
> 找不到本地路径。
    
## <a name="see-also"></a>另请参阅



[ScUNCFromLocalPath](scuncfromlocalpath.md)

