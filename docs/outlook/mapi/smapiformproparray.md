---
title: SMAPIFormPropArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SMAPIFormPropArray
api_type:
- COM
ms.assetid: bb243bc4-4974-4ad6-aa76-2426c1ebe84b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d907f2e8ecb9b6126898ff35b13427b088af9561
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778825"
---
# <a name="smapiformproparray"></a>SMAPIFormPropArray

  
  
**适用于**： Outlook 
  
包含一个[SMAPIFormProp](smapiformprop.md)结构数组。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiform.h  <br/> |
|相关的宏：  <br/> |[CbMAPIFormPropArray](cbmapiformproparray.md) <br/> |
   
```cpp
typedef struct
{
  ULONG cProps;
  ULONG ulPad;
  SMAPIFormProp aFormProp[MAPI_DIM];
} SMAPIFormPropArray, FAR * LPMAPIFORMPROPARRAY;

```

## <a name="members"></a>Members

 **cProps**
  
> 在**aFormProp**成员数组中的命名属性的计数。 
    
 **ulPad**
  
>  8 个字节用于保证正确的对齐方式的边距。 
    
 **aFormProp**
  
> 窗体属性的数组。
    
## <a name="remarks"></a>说明

**SMAPIFormPropArray**结构作为参数传递给以下方法： 
  
- [IMAPIFormInfo::CalcFormPropSet](imapiforminfo-calcformpropset.md)
    
- [IMAPIFormMgr::CalcFormPropSet](imapiformmgr-calcformpropset.md)
    
- [IMAPIFormContainer::CalcFormPropSet](imapiformcontainer-calcformpropset.md)
    
## <a name="see-also"></a>另请参阅



[CbMAPIFormPropArray](cbmapiformproparray.md)
  
[SMAPIFormProp](smapiformprop.md)


[MAPI 结构](mapi-structures.md)

