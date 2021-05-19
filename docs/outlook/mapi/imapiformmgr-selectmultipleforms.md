---
title: IMAPIFormMgrSelectMultipleForms
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgr.SelectMultipleForms
api_type:
- COM
ms.assetid: 172f8f53-b837-4286-9236-3f72806d7f1f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c40d853c49645638c2ec4001d86e64a1b2d2e381
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420309"
---
# <a name="imapiformmgrselectmultipleforms"></a>IMAPIFormMgr::SelectMultipleForms

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
显示一个对话框，允许用户选择多个表单，并返回描述这些表单的表单信息对象数组。
  
```cpp
HRESULT SelectMultipleForms(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPCSTR pszTitle,
  LPMAPIFOLDER pfld,
  LPMAPIFORMINFOARRAY pfrminfoarray,
  LPMAPIFORMINFOARRAY FAR * ppfrminfoarray
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]所显示对话框的父窗口的句柄。 
    
 _ulFlags_
  
> [in]控制传入字符串类型的标志位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 传入字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。
    
 _pszTitle_
  
> [in]指向包含对话框标题的字符串的指针。 如果  _pszTitle_ 参数为 NULL，则提供表单的表单库提供程序将提供默认标题。 
    
 _pfld_
  
> [in]指向从中选择窗体的文件夹的指针。 如果  _pfld_ 参数为 NULL，则从本地、个人或组织表单容器中选择表单。 
    
 _pfrminfoarray_
  
> [in]指向预先为用户选择表单信息对象的数组的指针。
    
 _ppfrminfoarray_
  
> [out]指向返回的表单信息对象数组的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回预期值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置 MAPI_UNICODE 标志，而实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。
    
MAPI_E_USER_CANCEL 
  
> 用户通常通过单击对话框中的"取消 **"按钮来** 取消操作。 
    
## <a name="remarks"></a>备注

表单查看器调用 **IMAPIFormMgr：：SelectMultipleForms** 方法，以首先显示一个对话框，使用户能够选择多个表单，然后检索描述所选表单的表单信息对象数组。 **SelectMultipleForms** 对话框显示所有窗体，无论它们是否 (，即其隐藏属性是否) 。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果表单查看器在  _ulFlags_ MAPI_UNICODE传递该标志，则所有字符串都是 Unicode。 如果传递了 Unicode 字符串，则不支持 Unicode MAPI_E_BAD_CHARWIDTH返回MAPI_UNICODE提供程序。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)

