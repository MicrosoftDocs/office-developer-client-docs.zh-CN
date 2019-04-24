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
ms.openlocfilehash: e5adc7d0c317d8b803645d78227777998d7d241f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32347836"
---
# <a name="hrgetoneprop"></a>HrGetOneProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
从属性接口检索单个属性的值, 即从[IMAPIProp](imapipropiunknown.md)派生的接口。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
HrGetOneProp(
  LPMAPIPROP pmp,
  ULONG ulPropTag,
  LPSPropValue FAR * ppprop
);
```

## <a name="parameters"></a>参数

 _pmp_
  
> 实时指向要从中检索属性值的[IMAPIProp](imapipropiunknown.md)接口的指针。 
    
 _ulPropTag_
  
> 实时要检索的属性的属性标记。 
    
 _ppprop_
  
> 排除指向用于定义检索到的属性值的返回的[SPropValue](spropvalue.md)结构的指针的指针。 
    
## <a name="return-value"></a>返回值

MAPI_E_NOT_FOUND 
  
> 请求的属性在指定的接口中不可用。
    
## <a name="remarks"></a>注解

与[IMAPIProp:: GetProps](imapiprop-getprops.md)方法不同, **HrGetOneProp**函数永远不会返回任何警告。 由于它只检索一个属性, 它只是成功或失败。 若要检索多个属性, **GetProps**速度更快。 
  
您可以使用[HrSetOneProp](hrsetoneprop.md)函数设置或更改单个属性。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFunctions  <br/> |GetMAPIObjectType  <br/> |MFCMAPI 使用**HrGetOneProp**方法来检索对象的类型。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

