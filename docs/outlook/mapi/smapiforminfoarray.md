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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e274e24d9aff30bb39b1865306477164d413d9a8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319171"
---
# <a name="smapiforminfoarray"></a>SMAPIFormInfoArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含指向表单信息对象的指针数组。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform  <br/> |
|相关宏:  <br/> |[CbMAPIFormInfoArray](cbmapiforminfoarray.md) <br/> |
   
```cpp
typedef struct
{
  ULONG cForms;
  LPMAPIFORMINFO aFormInfo[MAPI_DIM];
} SMAPIFormInfoArray, FAR * LPSMAPIFORMINFOARRAY;

```

## <a name="members"></a>Members

 **cForms**
  
> 由**aFormInfo**成员指向的数组中的指针计数。 
    
 **aFormInfo**
  
> 指向指向表单信息对象的指针的数组的指针。
    
## <a name="remarks"></a>注解

在以下方法中, **SMAPIFormInfoArray**结构作为参数传递: 
  
- [IMAPIFormMgr::ResolveMultipleMessageClasses](imapiformmgr-resolvemultiplemessageclasses.md)
    
- [IMAPIFormMgr::CalcFormPropSet](imapiformmgr-calcformpropset.md)
    
- [IMAPIFormMgr::SelectMultipleForms](imapiformmgr-selectmultipleforms.md)
    
- [IMAPIFormContainer::ResolveMultipleMessageClasses](imapiformcontainer-resolvemultiplemessageclasses.md)
    
## <a name="see-also"></a>另请参阅



[MAPI 结构](mapi-structures.md)

