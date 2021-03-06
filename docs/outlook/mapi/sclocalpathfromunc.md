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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432231"
---
# <a name="sclocalpathfromunc"></a>ScLocalPathFromUNC

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
查找 UNC 路径中给定通用命名约定 (本地) 路径。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
SCODE ScLocalPathFromUNC(
  LPSTR szUNC,
  LPSTR szLocal,
  UINT cchLocal
);
```

## <a name="parameters"></a>参数

 _szUNC_
  
> [in]文件或目录 \\ 的格式为 [ _server_] \[ _share_] \[ _path_] 的路径。
    
 _szLocal_
  
> [out]与 szUNC 参数相同的文件或目录的格式 [ _drive：_] \[ _path_  ] 的路径。 
    
 _cchLocal_
  
> [in]输出字符串的缓冲区大小。
    
## <a name="return-value"></a>返回值

S_OK
  
> 已成功找到本地路径。
    
MAPI_E_TOO_BIG
  
>  _szLocal_ 不够大，不足以容纳结果。 
    
S_FALSE
  
> UNC 字符串已经是本地路径。
    
MAPI_E_NOT_FOUND
  
> 未找到本地路径。
    
## <a name="see-also"></a>另请参阅



[ScUNCFromLocalPath](scuncfromlocalpath.md)

