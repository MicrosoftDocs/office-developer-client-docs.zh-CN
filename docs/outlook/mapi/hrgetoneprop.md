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
ms.openlocfilehash: 4dcdce72781669988a0cb15eb9b3a7cd73494bfb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775184"
---
# <a name="hrgetoneprop"></a>HrGetOneProp

  
  
**适用于**： Outlook 
  
从属性界面，即接口派生自[IMAPIProp](imapipropiunknown.md)检索单个属性的值。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
HrGetOneProp(
  LPMAPIPROP pmp,
  ULONG ulPropTag,
  LPSPropValue FAR * ppprop
);
```

## <a name="parameters"></a>参数

 _pmp_
  
> [in]是要检索属性值的[IMAPIProp](imapipropiunknown.md)接口的指针。 
    
 _ulPropTag_
  
> [in]要检索的属性的属性标记。 
    
 _ppprop_
  
> [输出]返回[SPropValue](spropvalue.md)结构定义检索的属性值为指针的指针。 
    
## <a name="return-value"></a>返回值

MAPI_E_NOT_FOUND 
  
> 从指定的接口请求的属性不可用。
    
## <a name="remarks"></a>说明

不同的[IMAPIProp::GetProps](imapiprop-getprops.md)方法， **HrGetOneProp**函数永远不会返回任何警告。 检索只有一个属性，因为它只是成功或失败。 用于检索多个属性， **GetProps**是更快。 
  
您可以设置或更改单个属性与[HrSetOneProp](hrsetoneprop.md)函数。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIFunctions.cpp  <br/> |GetMAPIObjectType  <br/> |MFCMAPI 使用**HrGetOneProp**方法检索的对象的类型。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

