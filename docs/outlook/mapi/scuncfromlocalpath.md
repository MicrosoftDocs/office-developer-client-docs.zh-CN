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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414534"
---
# <a name="scuncfromlocalpath"></a>ScUNCFromLocalPath

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
查找 UNC 中与给定本地 (对应的) 通用命名约定。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
SCODE ScUNCFromLocalPath(
  LPSTR szLocal,
  LPSTR szUNC,
  UINT cchUNC
);
```

## <a name="parameters"></a>参数

 _szLocal_
  
> [in]文件或目录的格式为 [ _drive：_] \[ _path_] 的路径。
    
 _szUNC_
  
> [out]与 \\  \[  \[ _szLocal_ 参数相同的文件或目录的格式 [ server ] share ] path ] 的路径。 
    
 _cchUNC_
  
> [in]输出字符串的缓冲区大小。
    
## <a name="return-value"></a>返回值

S_OK
  
> 成功找到对应的 UNC 路径。
    
MAPI_E_INVALID_PARAMETER
  
> 一个或多个参数无效。
    
MAPI_E_TOO_BIG
  
>  _szUNC_ 不够大，无法容纳结果。 
    
S_FALSE
  
> 本地路径已经是 UNC 字符串。
    
## <a name="see-also"></a>另请参阅



[ScLocalPathFromUNC](sclocalpathfromunc.md)

