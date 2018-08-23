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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9c6a6d210230fc305aef46371c22f67b3d445a81
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576580"
---
# <a name="imapiformcontainercalcformpropset"></a>IMAPIFormContainer::CalcFormPropSet

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
返回一个数组由安装窗体容器中的所有窗体的属性。
  
```cpp
HRESULT CalcFormPropSet(
  ULONG ulFlags,
  LPMAPIFORMPROPARRAY FAR * ppResults
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]位掩码的标志，控制如何返回_ppResults_参数中的属性数组。 可以设置以下标志： 
    
FORMPROPSET_INTERSECTION 
  
> 返回的数组包含窗体的属性的交点。
    
FORMPROPSET_UNION 
  
> 返回的数组包含窗体的属性的合并。
    
MAPI_UNICODE 
  
> 数组中返回的字符串是 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。
    
 _ppResults_
  
> [输出]指向返回[SMAPIFormPropArray](smapiformproparray.md)结构的指针的指针。 此结构包含所有安装的表单所使用的属性。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_BAD_CHARWIDTH 
  
> 既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。
    
## <a name="remarks"></a>注解

客户端应用程序调用**IMAPIFormContainer::CalcFormPropSet**方法以获取属性由安装窗体容器中的所有窗体的数组。 **IMAPIFormContainer::CalcFormPropSet**工作[IMAPIFormMgr::CalcFormPropSet](imapiformmgr-calcformpropset.md)方法，如之处在于它运行在某个特定的容器中注册的每个窗体上。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

如果传递 MAPI_UNICODE，窗体库提供程序不支持 Unicode 字符串应返回 MAPI_E_BAD_CHARWIDTH。
  
## <a name="notes-to-callers"></a>给调用方的说明

 **IMAPIFormContainer::CalcFormPropSet**采用交集或的窗体的属性集，具体取决于的标记设置_ulFlags_参数中的联合，并将返回包含**SMAPIFormPropArray**结构生成组的属性。 
  
如果客户端传入_ulFlags_MAPI_UNICODE 标志，所有返回的字符串是在 Unicode。
  
## <a name="see-also"></a>另请参阅



[IMAPIFormMgr::CalcFormPropSet](imapiformmgr-calcformpropset.md)
  
[SMAPIFormPropArray](smapiformproparray.md)
  
[IMAPIFormContainer : IUnknown](imapiformcontaineriunknown.md)

