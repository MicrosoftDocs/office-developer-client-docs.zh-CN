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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321670"
---
# <a name="imapiformmgrselectform"></a>IMAPIFormMgr::SelectForm

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
显示一个对话框, 使用户能够选择窗体, 并返回描述该窗体的窗体信息对象。
  
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
  
> 实时显示的对话框的父窗口的句柄。 
    
 _ulFlags_
  
> 实时标志的位掩码, 用于控制传入的字符串的类型。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。
    
 _pszTitle_
  
> 实时指向包含对话框标题的字符串的指针。 如果_pszTitle_参数为 NULL, 则表单库提供程序将提供一个默认标题。 
    
 _pfld_
  
> 实时指向要从中选择表单的文件夹的指针。 如果_pfld_参数为 NULL, 则可以从 "本地"、"个人" 或 "组织" 表单容器中选择表单。 
    
 _ppfrminfoReturned_
  
> 排除指向指向返回的表单信息对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。
    
MAPI_E_USER_CANCEL 
  
> 用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。 
    
## <a name="remarks"></a>注解

表单查看者调用**IMAPIFormMgr:: SelectForm**方法, 首先显示一个对话框, 使用户能够选择表单, 然后检索描述选定表单的表单信息对象。 对话框限制用户选择单个窗体。 
  
## <a name="notes-to-callers"></a>给调用方的说明

" **SelectForm** " 对话框仅显示未隐藏的表单 (即, 其隐藏属性已清除的表单)。 如果表单查看器在_ulFlags_参数中传递 MAPI_UNICODE 标志, 则所有字符串均为 UNICODE。 如果 MAPI_UNICODE 已传递, 则不支持 Unicode 字符串的表单库提供程序应返回 MAPI_E_BAD_CHARWIDTH。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|FolderDlg  <br/> |CFolderDlg:: OnSelectForm  <br/> |MFCMAPI 使用**IMAPIFormMgr:: SelectForm**方法选择窗体, 并将有关该窗体的信息发送到一个或多个日志。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

