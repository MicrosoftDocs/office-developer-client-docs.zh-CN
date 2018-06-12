---
title: SMAPIFormInfoArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SMAPIFormInfoArray
api_type:
- COM
ms.assetid: f5eeb75d-debb-4ac1-b239-e8e852460ce0
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 6389bbf2094f51711d80896db0db9862059826cc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778833"
---
# <a name="smapiforminfoarray"></a>SMAPIFormInfoArray

  
  
**适用于**： Outlook 
  
包含指向窗体信息对象的数组。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiform.h  <br/> |
|相关的宏：  <br/> |[CbMAPIFormInfoArray](cbmapiforminfoarray.md) <br/> |
   
```cpp
typedef struct
{
  ULONG cForms;
  LPMAPIFORMINFO aFormInfo[MAPI_DIM];
} SMAPIFormInfoArray, FAR * LPSMAPIFORMINFOARRAY;

```

## <a name="members"></a>成员

 **cForms**
  
> 计数的数组中的指针指向由**aFormInfo**成员。 
    
 **aFormInfo**
  
> 为数组对窗体信息对象的指针的指针。
    
## <a name="remarks"></a>备注

**SMAPIFormInfoArray**结构作为中的以下方法的参数传递： 
  
- [IMAPIFormMgr::ResolveMultipleMessageClasses](imapiformmgr-resolvemultiplemessageclasses.md)
    
- [IMAPIFormMgr::CalcFormPropSet](imapiformmgr-calcformpropset.md)
    
- [IMAPIFormMgr::SelectMultipleForms](imapiformmgr-selectmultipleforms.md)
    
- [IMAPIFormContainer::ResolveMultipleMessageClasses](imapiformcontainer-resolvemultiplemessageclasses.md)
    
## <a name="see-also"></a>另请参阅



[MAPI 结构](mapi-structures.md)

