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
  
返回由安装在表单容器中的所有表单使用的属性数组。
  
```cpp
HRESULT CalcFormPropSet(
  ULONG ulFlags,
  LPMAPIFORMPROPARRAY FAR * ppResults
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]控制  _ppResults_ 参数中属性数组的返回方式的标志位掩码。 可以设置以下标志： 
    
FORMPROPSET_INTERSECTION 
  
> 返回的数组包含窗体属性的交集。
    
FORMPROPSET_UNION 
  
> 返回的数组包含窗体属性的并集。
    
MAPI_UNICODE 
  
> 数组中返回的字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。
    
 _ppResults_
  
> [out]指向返回的 [SMAPIFormPropArray 结构的指针的](smapiformproparray.md) 指针。 此结构包含已安装的表单使用的所有属性。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置 MAPI_UNICODE 标志，而实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。
    
## <a name="remarks"></a>备注

客户端应用程序调用 **IMAPIFormContainer：：CalcFormPropSet** 方法以获取表单容器中安装的所有表单所使用的属性数组。 **IMAPIFormContainer：：CalcFormPropSet** 的工作方式与 [IMAPIFormMgr：：CalcFormPropSet](imapiformmgr-calcformpropset.md) 方法类似，只不过它在特定容器中注册的所有表单上运行。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果传递了 Unicode 字符串，则不支持 Unicode MAPI_E_BAD_CHARWIDTH返回MAPI_UNICODE提供程序。
  
## <a name="notes-to-callers"></a>给调用方的说明

 **IMAPIFormContainer：：CalcFormPropSet** 采用表单属性集的交集或联合，具体取决于  _ulFlags_ 参数中设置的标志，并返回一个 **SMAPIFormPropArray** 结构，其中包含生成的属性组。 
  
如果客户端在  _ulFlags_ 中传递 MAPI_UNICODE 标志，则返回的所有字符串都是 Unicode。
  
## <a name="see-also"></a>另请参阅



[IMAPIFormMgr::CalcFormPropSet](imapiformmgr-calcformpropset.md)
  
[SMAPIFormPropArray](smapiformproparray.md)
  
[IMAPIFormContainer : IUnknown](imapiformcontaineriunknown.md)

