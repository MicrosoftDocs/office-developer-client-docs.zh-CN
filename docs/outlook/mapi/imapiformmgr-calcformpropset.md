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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436424"
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
  
> [in]指向标识要返回其属性的表单的表单信息对象的数组的指针。
    
 _ulFlags_
  
> [in]控制  _ppResults_ 参数中属性数组的返回方式的标志位掩码。 可以设置以下标志： 
    
FORMPROPSET_INTERSECTION 
  
> 返回的数组包含表单属性的交集。
    
FORMPROPSET_UNION 
  
> 返回的数组包含表单属性的并集。
    
MAPI_UNICODE 
  
> 数组中返回的字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。
    
 _ppResults_
  
> [out]指向返回的 [SMAPIFormPropArray](smapiformproparray.md) 结构的指针的指针，其中包含表单使用的属性。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回预期值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置 MAPI_UNICODE 标志，而实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。
    
## <a name="remarks"></a>备注

表单查看器调用 **IMAPIFormMgr：：CalcFormPropSet** 方法以获取一组表单使用的属性的数组。 根据 _ulFlags_ 参数中设置的标志 **，CalcFormPropSet** 采用这些表单的属性集的交集或联合，并返回包含生成的属性组的 **SMAPIFormPropArray** 结构。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果表单查看器在  _ulFlags_ 参数中传递 MAPI_UNICODE 标志，则所有字符串应作为 Unicode 字符串返回。 如果传递了 Unicode 字符串，则不支持 Unicode MAPI_E_BAD_CHARWIDTH返回MAPI_UNICODE提供程序。 
  
## <a name="see-also"></a>另请参阅



[SMAPIFormPropArray](smapiformproparray.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)

