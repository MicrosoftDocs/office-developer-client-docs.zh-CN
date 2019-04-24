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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321593"
---
# <a name="imapiformmgrselectmultipleforms"></a>IMAPIFormMgr::SelectMultipleForms

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
显示一个对话框, 允许用户选择多个窗体, 并返回描述这些窗体的窗体信息对象的数组。
  
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
  
> 实时显示的对话框的父窗口的句柄。 
    
 _ulFlags_
  
> 实时标志的位掩码, 用于控制传入的字符串的类型。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。
    
 _pszTitle_
  
> 实时指向包含对话框标题的字符串的指针。 如果_pszTitle_参数为 NULL, 则提供表单的表单库提供程序提供默认标题。 
    
 _pfld_
  
> 实时指向要从中选择表单的文件夹的指针。 如果_pfld_参数为 NULL, 则从 "本地"、"个人" 或 "组织" 表单容器中选择表单。 
    
 _pfrminfoarray_
  
> 实时一个指针, 指向为用户预选的表单信息对象的数组。
    
 _ppfrminfoarray_
  
> 排除指向指向表单信息对象的返回数组的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的一个或一些值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。
    
MAPI_E_USER_CANCEL 
  
> 用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。 
    
## <a name="remarks"></a>注解

表单查看者调用**IMAPIFormMgr:: SelectMultipleForms**方法, 首先显示一个对话框, 使用户可以选择多个表单, 然后检索描述所选表单的表单信息对象的数组。 " **SelectMultipleForms** " 对话框将显示所有窗体, 无论它们是否隐藏 (即, 无论其隐藏属性是否清楚)。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果表单查看器在_ulFlags_参数中传递 MAPI_UNICODE 标志, 则所有字符串均为 UNICODE。 如果 MAPI_UNICODE 已传递, 则不支持 Unicode 字符串的表单库提供程序应返回 MAPI_E_BAD_CHARWIDTH。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)

