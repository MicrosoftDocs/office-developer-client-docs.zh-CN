---
title: HrGetOneProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- HrGetOneProp
api_type:
- HeaderDef
ms.assetid: 8d0a381a-e714-4663-9a57-b0e1cdbd6ba7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 95273bf6025d6ef995d7c21c0e44bdbbf59072f6
ms.sourcegitcommit: fb521c23df785c9c3aefa5062272b2630a32e587
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2021
ms.locfileid: "52589171"
---
# <a name="hrgetoneprop"></a>HrGetOneProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
从属性接口（即派生自 [IMAPIProp](imapipropiunknown.md)的接口）检索单个属性的值。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
HRESULT HrGetOneProp(
  LPMAPIPROP pmp,
  ULONG ulPropTag,
  LPSPropValue FAR * ppprop
);
```

## <a name="parameters"></a>参数

 _pmp_
  
> [in]指向要检索属性值的 [IMAPIProp](imapipropiunknown.md) 接口的指针。 
    
 _ulPropTag_
  
> [in]要检索的属性的属性标记。 
    
 _ppprop_
  
> [out]指向定义检索到的属性值的 [返回 SPropValue](spropvalue.md) 结构的指针的指针。 
    
## <a name="return-value"></a>返回值

MAPI_E_NOT_FOUND 
  
> 请求的属性在指定的接口中不可用。
    
## <a name="remarks"></a>备注

与 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法不同 **，HrGetOneProp** 函数从不返回任何警告。 因为它只检索一个属性，所以它要么成功要么失败。 对于检索多个属性 **，GetProps** 速度更快。 
  
可以使用 [HrSetOneProp](hrsetoneprop.md) 函数设置或更改单个属性。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFunctions.cpp  <br/> |GetMAPIObjectType  <br/> |MFCMAPI 使用 **HrGetOneProp** 方法检索对象的类型。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

