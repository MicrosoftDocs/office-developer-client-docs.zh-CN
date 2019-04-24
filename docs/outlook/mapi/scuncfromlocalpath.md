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
ms.openlocfilehash: b53dd9aaaf18dba5c7e33e0bc7d984de757634a4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358770"
---
# <a name="scuncfromlocalpath"></a>ScUNCFromLocalPath

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
查找给定本地路径对应的通用命名约定 (UNC) 路径。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
SCODE ScUNCFromLocalPath(
  LPSTR szLocal,
  LPSTR szUNC,
  UINT cchUNC
);
```

## <a name="parameters"></a>参数

 _szLocal_
  
> 实时文件或目录的格式 [_驱动器:_]\[ _路径_] 中的路径。
    
 _szUNC_
  
> 排除与_szLocal_参数的文件\\或目录的格式 [ _server_]\[ _share_]\[ _path_] 中的路径。 
    
 _cchUNC_
  
> 实时输出字符串的缓冲区大小。
    
## <a name="return-value"></a>返回值

S_OK
  
> 已成功找到对应的 UNC 路径。
    
MAPI_E_INVALID_PARAMETER
  
> 一个或多个参数无效。
    
MAPI_E_TOO_BIG
  
>  _szUNC_的大小不足以容纳结果。 
    
S_FALSE
  
> 本地路径已是 UNC 字符串。
    
## <a name="see-also"></a>另请参阅



[ScLocalPathFromUNC](sclocalpathfromunc.md)

