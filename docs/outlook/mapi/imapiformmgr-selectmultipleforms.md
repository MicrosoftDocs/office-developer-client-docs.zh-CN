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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 096437f10c5b992a1db55f6a856c38021a81b99a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775452"
---
# <a name="imapiformmgrselectmultipleforms"></a>IMAPIFormMgr::SelectMultipleForms

  
  
**适用于**： Outlook 
  
显示一个对话框，使用户能够选择多个表单，并返回介绍这些表单的信息对象的窗体的数组。
  
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
  
> [in]显示的对话框中的父窗口句柄。 
    
 _ulFlags_
  
> [in]位掩码的标志的控制传入的字符串的类型。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。
    
 _pszTitle_
  
> [in]一个指向一个字符串，包含对话框的标题。 如果_pszTitle_参数为 NULL，提供窗体的窗体库提供程序提供的默认标题。 
    
 _pfld_
  
> [in]指向文件夹从中选择窗体的指针。 如果_pfld_参数为 NULL，则从本地、 个人，或组织窗体容器中选择窗体。 
    
 _pfrminfoarray_
  
> [in]一个指向未预先选择用户的窗体信息对象的数组。
    
 _ppfrminfoarray_
  
> [输出]指向到窗体信息对象返回的数组的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功，并返回预期的值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。
    
MAPI_E_USER_CANCEL 
  
> 用户取消操作，通常通过单击对话框中的**取消**按钮。 
    
## <a name="remarks"></a>说明

表单查看器调用**IMAPIFormMgr::SelectMultipleForms**方法到第一个存在一个对话框，使用户能够选择多个窗体，然后检索数组表单信息的对象的描述所选的形式。 **SelectMultipleForms**对话框中显示所有窗体，它们处于隐藏状态 （也就是说，不管其隐藏的属性清除)。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

如果表单查看器_ulFlags_参数中传递 MAPI_UNICODE 标志，所有字符串都是在 Unicode。 如果传递 MAPI_UNICODE，窗体库提供程序不支持 Unicode 字符串应返回 MAPI_E_BAD_CHARWIDTH。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)

