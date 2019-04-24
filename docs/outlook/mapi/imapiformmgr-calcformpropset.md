---
title: IMAPIFormMgrCalcFormPropSet
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgr.CalcFormPropSet
api_type:
- COM
ms.assetid: ab302bfd-5cff-49b4-b0d2-308ae5af478d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bf072aba27c90b7cea80c464e17fafb47524b695
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342082"
---
# <a name="imapiformmgrcalcformpropset"></a>IMAPIFormMgr::CalcFormPropSet

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回一组窗体使用的属性的数组。
  
```cpp
HRESULT CalcFormPropSet(
  LPSMAPIFORMINFOARRAY pfrminfoarray,
  ULONG ulFlags,
  LPMAPIFORMPROPARRAY FAR * ppResults
);
```

## <a name="parameters"></a>参数

 _pfrminfoarray_
  
> 实时指向表单信息对象数组的指针, 这些对象标识要为其返回属性的窗体。
    
 _ulFlags_
  
> 实时标志的位掩码, 用于控制如何返回_ppResults_参数中的属性数组。 可以设置以下标志: 
    
FORMPROPSET_INTERSECTION 
  
> 返回的数组包含窗体属性的交集。
    
FORMPROPSET_UNION 
  
> 返回的数组包含表单属性的联合。
    
MAPI_UNICODE 
  
> 数组中返回的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。
    
 _ppResults_
  
> 排除指向返回的[SMAPIFormPropArray](smapiformproparray.md)结构的指针的指针, 该指针包含表单使用的属性。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的一个或一些值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。
    
## <a name="remarks"></a>注解

表单查看者调用**IMAPIFormMgr:: CalcFormPropSet**方法以获取一组表单使用的属性的数组。 **CalcFormPropSet**采用相交或联合这些 forms 的属性集, 具体取决于在_ulFlags_参数中设置的标志, 并且它将返回一个**SMAPIFormPropArray**结构, 其中包含生成的一组属性. 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果表单查看器在_ulFlags_参数中传递 MAPI_UNICODE 标志, 则所有字符串都应以 UNICODE 字符串的形式返回。 如果 MAPI_UNICODE 已传递, 则不支持 Unicode 字符串的表单库提供程序应返回 MAPI_E_BAD_CHARWIDTH。 
  
## <a name="see-also"></a>另请参阅



[SMAPIFormPropArray](smapiformproparray.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)

