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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: abd2a3e2a1a810f902ad977413c89f2e8b0113a0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775408"
---
# <a name="imapiformmgrcalcformpropset"></a>IMAPIFormMgr::CalcFormPropSet

  
  
**适用于**： Outlook 
  
返回一个数组的一组表单使用的属性。
  
```cpp
HRESULT CalcFormPropSet(
  LPSMAPIFORMINFOARRAY pfrminfoarray,
  ULONG ulFlags,
  LPMAPIFORMPROPARRAY FAR * ppResults
);
```

## <a name="parameters"></a>参数

 _pfrminfoarray_
  
> [in]一个指向确定要为其返回属性的窗体的窗体信息对象的数组。
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何返回_ppResults_参数中的属性数组。 可以设置以下标志： 
    
FORMPROPSET_INTERSECTION 
  
> 返回的数组包含窗体的属性的交点。
    
FORMPROPSET_UNION 
  
> 返回的数组包含窗体的属性的合并。
    
MAPI_UNICODE 
  
> 数组中返回的字符串是 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。
    
 _ppResults_
  
> [输出]指向返回[SMAPIFormPropArray](smapiformproparray.md)结构，其中包含表单使用的属性的指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功，并返回预期的值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。
    
## <a name="remarks"></a>说明

表单查看器调用**IMAPIFormMgr::CalcFormPropSet**方法以获取的属性的一组窗体使用数组。 **CalcFormPropSet**采用任一交集或联合这些窗体的属性的设置，具体取决于的标记设置中_ulFlags_参数，并将返回**SMAPIFormPropArray**结构，其中包含的生成组属性。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

如果表单查看器_ulFlags_参数中传递 MAPI_UNICODE 标志，应以 Unicode 字符串形式返回所有字符串。 如果传递 MAPI_UNICODE，窗体库提供程序不支持 Unicode 字符串应返回 MAPI_E_BAD_CHARWIDTH。 
  
## <a name="see-also"></a>另请参阅



[SMAPIFormPropArray](smapiformproparray.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)

