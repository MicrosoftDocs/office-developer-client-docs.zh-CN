---
title: FBadEntryList
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- FBadEntryList
api_type:
- HeaderDef
ms.assetid: 270c47c3-ae68-4995-b304-27f861b350d6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 113628ef5487bc66a07d1367c938ed178a8e32ec
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582908"
---
# <a name="fbadentrylist"></a>FBadEntryList

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
验证 MAPI 项标识符的列表。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapival.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |服务提供商  <br/> |
   
```cpp
BOOL FBadEntryList(
  LPENTRYLIST lpEntryList
);
```

## <a name="parameters"></a>参数

 _lpEntryList_
  
> [in]指向[ENTRYLIST](entrylist.md)结构，其中包含要验证的项标识符的数组。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 一个或多个列出的项标识符是无效。 
    
FALSE 
  
> 所有列出的项标识符都是有效的。
    
## <a name="remarks"></a>注解

**FBadEntryList**函数确定是否已正确生成条目标识符列表。 无效的示例是标识符的一个已正确分配的内存或大小不正确的标识符。 
  

