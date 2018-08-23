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
ms.openlocfilehash: 96dddc438df67b76f854827eab4dc3e210523243
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588144"
---
# <a name="fbadrglpnameid"></a>FBadRglpNameID

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
验证数组介绍命名属性的结构，并验证其分配。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapival.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |服务提供商  <br/> |
   
```cpp
BOOL FBadRglpNameID(
  LPMAPINAMEID FAR * lppNameId,
  ULONG cNames
);
```

## <a name="parameters"></a>参数

 _lppNameId_
  
> [in]指向[MAPINAMEID](mapinameid.md)结构描述命名的属性的数组。 
    
 _Cname_
  
> [in]由_lppNameId_参数指向的数组中的命名的属性结构的计数。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 一个或多个指定的属性名称结构无效。 
    
FALSE 
  
> 指定的属性名称结构均有效。
    
## <a name="remarks"></a>注解

调用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)或[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)设置时，可以使用**FBadRglpNameID**函数。 
  

