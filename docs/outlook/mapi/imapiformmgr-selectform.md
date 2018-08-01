---
title: IMAPIFormMgrSelectForm
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgr.SelectForm
api_type:
- COM
ms.assetid: c1cfe71b-01f3-429a-8b4c-73191a2ffea0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b481eaf00b7568da5f02ffa3301e8f2698a98e1e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775436"
---
# <a name="imapiformmgrselectform"></a>IMAPIFormMgr::SelectForm

  
  
**适用于**： Outlook 
  
显示一个对话框，允许用户选择一个窗体，并返回描述该窗体的窗体信息对象。
  
```cpp
HRESULT SelectForm(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPCSTR pszTitle,
  LPMAPIFOLDER pfld,
  LPMAPIFORMINFO FAR * ppfrminfoReturned
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
  
> [in]一个指向一个字符串，包含对话框的标题。 如果_pszTitle_参数为 NULL，表单库提供程序提供的默认标题。 
    
 _pfld_
  
> [in]指向文件夹从中选择窗体的指针。 如果_pfld_参数为 NULL，则可以从本地、 个人，或组织窗体容器选择窗体。 
    
 _ppfrminfoReturned_
  
> [输出]指向返回窗体信息对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_BAD_CHARWIDTH 
  
> 既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。
    
MAPI_E_USER_CANCEL 
  
> 用户取消操作，通常通过单击对话框中的**取消**按钮。 
    
## <a name="remarks"></a>说明

表单查看器调用**IMAPIFormMgr::SelectForm**方法向第一个存在一个对话框，允许用户选择一个窗体，然后检索窗体信息对象的介绍选定的窗体。 对话框将约束用户选择单个窗体。 
  
## <a name="notes-to-callers"></a>给调用方的说明

**SelectForm**对话框显示处于非隐藏状态的表单 （即，其隐藏属性的表单清除）。 如果表单查看器_ulFlags_参数中传递 MAPI_UNICODE 标志，所有字符串都是在 Unicode。 如果传递 MAPI_UNICODE，窗体库提供程序不支持 Unicode 字符串应返回 MAPI_E_BAD_CHARWIDTH。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|FolderDlg.cpp  <br/> |CFolderDlg::OnSelectForm  <br/> |MFCMAPI 使用**IMAPIFormMgr::SelectForm**方法选择一个窗体，并将窗体的信息发送到一个或多个日志。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

