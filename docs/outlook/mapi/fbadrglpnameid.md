---
title: FBadRglpNameID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FBadRglpNameID
api_type:
- COM
ms.assetid: fec5d5ac-bca6-4fff-b264-45cdb6b37f55
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4eef7c0b1078cb9e7ced21e2403f0b3948362d6c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434828"
---
# <a name="fbadrglpnameid"></a>FBadRglpNameID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
验证描述命名属性的结构数组并验证其分配。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapival.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |服务提供程序  <br/> |
   
```cpp
BOOL FBadRglpNameID(
  LPMAPINAMEID FAR * lppNameId,
  ULONG cNames
);
```

## <a name="parameters"></a>参数

 _lppNameId_
  
> [in]指向描述命名属性 [的 MAPINAMEID](mapinameid.md) 结构的数组的指针。 
    
 _cNames_
  
> [in]  _lppNameId_ 参数指向的数组中的命名属性结构计数。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 一个或多个指定的属性名称结构无效。 
    
FALSE 
  
> 指定的属性名称结构均有效。
    
## <a name="remarks"></a>备注

在设置对 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md)或 [IMAPIProp：：GetNamesFromIDs](imapiprop-getnamesfromids.md)的调用时，可以使用 **FBadRglpNameID** 函数。 
  

