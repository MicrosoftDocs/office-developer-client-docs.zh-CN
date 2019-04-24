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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e7607a57da5b618a20d6c8e360c7e3cb4f933856
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351245"
---
# <a name="sclocalpathfromunc"></a>ScLocalPathFromUNC

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
查找给定的通用命名约定 (UNC) 路径对应的本地路径。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
SCODE ScLocalPathFromUNC(
  LPSTR szUNC,
  LPSTR szLocal,
  UINT cchLocal
);
```

## <a name="parameters"></a>参数

 _szUNC_
  
> 实时文件或目录的格式\\[ _server_]\[ _share_]\[ _path_] 中的路径。
    
 _szLocal_
  
> 排除与_szUNC_参数的文件或目录的格式 [ _drive:_]\[ _路径_] 的路径。 
    
 _cchLocal_
  
> 实时输出字符串的缓冲区大小。
    
## <a name="return-value"></a>返回值

S_OK
  
> 已成功定位本地路径。
    
MAPI_E_TOO_BIG
  
>  _szLocal_的大小不足以容纳结果。 
    
S_FALSE
  
> UNC 字符串已经是本地路径。
    
MAPI_E_NOT_FOUND
  
> 找不到本地路径。
    
## <a name="see-also"></a>另请参阅



[ScUNCFromLocalPath](scuncfromlocalpath.md)

