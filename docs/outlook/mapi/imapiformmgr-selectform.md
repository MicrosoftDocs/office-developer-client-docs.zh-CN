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
ms.openlocfilehash: c25f352e7fa607a46741164574a4ba91d4026edf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423578"
---
# <a name="imapiformmgrselectform"></a>IMAPIFormMgr::SelectForm

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
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
  
> [in]所显示对话框的父窗口的句柄。 
    
 _ulFlags_
  
> [in]控制传入字符串类型的标志位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 传入字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。
    
 _pszTitle_
  
> [in]指向包含对话框标题的字符串的指针。 如果  _pszTitle_ 参数为 NULL，则表单库提供程序会提供默认标题。 
    
 _pfld_
  
> [in]指向从中选择窗体的文件夹的指针。 如果  _pfld_ 参数为 NULL，可以从本地、个人或组织表单容器选择表单。 
    
 _ppfrminfoReturned_
  
> [out]指向返回的表单信息对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置 MAPI_UNICODE 标志，而实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。
    
MAPI_E_USER_CANCEL 
  
> 用户通常通过单击对话框中的"取消 **"按钮来** 取消操作。 
    
## <a name="remarks"></a>备注

表单查看者调用 **IMAPIFormMgr：：SelectForm** 方法，以首先显示一个对话框，使用户可以选择一个表单，然后检索描述所选表单的表单信息对象。 该对话框将限制用户选择单个窗体。 
  
## <a name="notes-to-callers"></a>给调用方的说明

**"SelectForm"** 对话框仅显示未隐藏 (，即具有隐藏属性的表单) 。 如果表单查看器在  _ulFlags_ MAPI_UNICODE传递该标志，则所有字符串都是 Unicode。 如果传递了 Unicode 字符串，则不支持 Unicode MAPI_E_BAD_CHARWIDTH返回MAPI_UNICODE提供程序。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|FolderDlg.cpp  <br/> |CFolderDlg：：OnSelectForm  <br/> |MFCMAPI 使用 **IMAPIFormMgr：：SelectForm** 方法选择表单并将有关表单的信息发送到一个或多个日志。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

