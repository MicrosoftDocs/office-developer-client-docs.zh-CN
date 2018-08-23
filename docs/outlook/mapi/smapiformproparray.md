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
ms.openlocfilehash: 389984f9d98ece6b2040edd741e3028fd7d766ed
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579310"
---
# <a name="smapiformproparray"></a>SMAPIFormPropArray

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
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
    
## <a name="remarks"></a>注解

**SMAPIFormPropArray**结构作为参数传递给以下方法： 
  
- [IMAPIFormInfo::CalcFormPropSet](imapiforminfo-calcformpropset.md)
    
- [IMAPIFormMgr::CalcFormPropSet](imapiformmgr-calcformpropset.md)
    
- [IMAPIFormContainer::CalcFormPropSet](imapiformcontainer-calcformpropset.md)
    
## <a name="see-also"></a>另请参阅



[CbMAPIFormPropArray](cbmapiformproparray.md)
  
[SMAPIFormProp](smapiformprop.md)


[MAPI 结构](mapi-structures.md)

