---
title: IMAPIFormContainerCalcFormPropSet
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormContainer.CalcFormPropSet
api_type:
- COM
ms.assetid: 594e3aac-a00f-422e-8e7a-949e4c9a3f8d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ec1933f80f211c7c381f9de6b15d414932b9a78e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414912"
---
# <a name="imapiformcontainercalcformpropset"></a>IMAPIFormContainer::CalcFormPropSet

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回安装在表单容器中的所有表单所使用的属性的数组。
  
```cpp
HRESULT CalcFormPropSet(
  ULONG ulFlags,
  LPMAPIFORMPROPARRAY FAR * ppResults
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时标志的位掩码, 用于控制如何返回_ppResults_参数中的属性数组。 可以设置以下标志: 
    
FORMPROPSET_INTERSECTION 
  
> 返回的数组包含窗体属性的交集。
    
FORMPROPSET_UNION 
  
> 返回的数组包含表单属性的联合。
    
MAPI_UNICODE 
  
> 数组中返回的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。
    
 _ppResults_
  
> 排除指向返回的[SMAPIFormPropArray](smapiformproparray.md)结构的指针的指针。 此结构包含已安装的表单所使用的所有属性。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。
    
## <a name="remarks"></a>说明

客户端应用程序调用**IMAPIFormContainer:: CalcFormPropSet**方法以获取在表单容器中安装的所有表单使用的属性数组。 **IMAPIFormContainer:: CalcFormPropSet**的工作方式与[IMAPIFormMgr:: CalcFormPropSet](imapiformmgr-calcformpropset.md)方法相同, 不同之处在于它在特定容器中注册的每个窗体上运行。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果 MAPI_UNICODE 已传递, 则不支持 Unicode 字符串的表单库提供程序应返回 MAPI_E_BAD_CHARWIDTH。
  
## <a name="notes-to-callers"></a>给调用方的说明

 **IMAPIFormContainer:: CalcFormPropSet**采用交集或 union of forms 属性集, 具体取决于_ulFlags_参数中设置的标志, 并且它将返回一个**SMAPIFormPropArray**结构, 其中包含生成的属性组。 
  
如果客户端在_ulFlags_中传递了 MAPI_UNICODE 标志, 则所有返回的字符串都是 UNICODE。
  
## <a name="see-also"></a>另请参阅



[IMAPIFormMgr::CalcFormPropSet](imapiformmgr-calcformpropset.md)
  
[SMAPIFormPropArray](smapiformproparray.md)
  
[IMAPIFormContainer : IUnknown](imapiformcontaineriunknown.md)

