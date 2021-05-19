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
ms.openlocfilehash: 50b6581dec8211968a49b204c6d9b1ba1c65bb62
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420064"
---
# <a name="smapiformproparray"></a>SMAPIFormPropArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含 [SMAPIFormProp 结构](smapiformprop.md) 数组。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform.h  <br/> |
|相关宏：  <br/> |[CbMAPIFormPropArray](cbmapiformproparray.md) <br/> |
   
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
  
> **aFormProp** 成员数组中命名属性的计数。 
    
 **ulPad**
  
>  用于保证正确对齐的八字节填充。 
    
 **aFormProp**
  
> 表单属性数组。
    
## <a name="remarks"></a>备注

**SMAPIFormPropArray** 结构作为参数传递给以下方法： 
  
- [IMAPIFormInfo::CalcFormPropSet](imapiforminfo-calcformpropset.md)
    
- [IMAPIFormMgr::CalcFormPropSet](imapiformmgr-calcformpropset.md)
    
- [IMAPIFormContainer::CalcFormPropSet](imapiformcontainer-calcformpropset.md)
    
## <a name="see-also"></a>另请参阅



[CbMAPIFormPropArray](cbmapiformproparray.md)
  
[SMAPIFormProp](smapiformprop.md)


[MAPI 结构](mapi-structures.md)

