---
title: IMAPIFormContainerInstallForm
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormContainer.InstallForm
api_type:
- COM
ms.assetid: b39ca52c-4dbe-41c0-9e1b-3998a9dc9742
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a0650033e4fea79046eac5757e3d0deb963c38e6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405084"
---
# <a name="imapiformcontainerinstallform"></a>IMAPIFormContainer::InstallForm

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将表单安装到表单库中。
  
```cpp
HRESULT InstallForm(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPCSTR szCfgPathName
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]该方法显示的任何对话框或窗口的父窗口的句柄。 除非  _客户端应用程序在 ulFlags_ 参数中设置 MAPI_DIALOG 标志，否则将忽略  _ulUIParam_ 参数。 如果未  _传递 ulUIParam_ 参数，MAPI_DIALOG为 NULL。 
    
 _ulFlags_
  
> [in]控制表单安装的位掩码标志。 可以设置以下标志：
    
MAPI_DIALOG 
  
> 显示一个对话框以提供进度信息或提示用户输入详细信息。 如果未设置此标志，则不显示任何对话框。
    
MAPI_UNICODE 
  
> 传入字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。
    
MAPIFORM_INSTALL_OVERWRITEONCONFLICT 
  
> 如果已存在另一个处理此表单处理的邮件类的表单，请将现有表单替换为此表单。 如果还显示"MAPI_DIALOG，则忽略此标志。 
    
 _szCfgPathName_
  
> [in]表单配置文件的路径。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
MAPI_E_EXTENDED_ERROR 
  
> 发生实现错误。 若要获取与 [错误关联的 MAPIERROR](mapierror.md) 结构，请调用 [IMAPIFormContainer：：GetLastError](imapiformcontainer-getlasterror.md) 方法。 
    
MAPI_E_USER_CANCEL 
  
> 用户通常通过单击对话框中的"取消"按钮来取消窗体的安装。 
    
## <a name="notes-to-implementers"></a>针对实现者的说明

表单库提供程序应填写 **MAPIERROR** 结构，并MAPI_E_EXTENDED_ERROR出现以下任一情况时返回一个表单库： 
  
- 找不到配置文件。
    
- 配置文件不可读。
    
- 配置文件无效。
    
## <a name="notes-to-callers"></a>给调用方的说明

客户端应用程序调用 **IMAPIFormContainer：：InstallForm** 方法将表单安装到特定的表单容器中。 _szCfgPathName_ 参数必须包含表单配置文件的路径 (即具有 .cfg 扩展名的文件，该文件描述表单及其实现) 。 _ulFlags_ 参数中的标志指定以下内容： 
  
- 如果MAPI_DIALOG，将显示用户界面，使安装表单的用户能够指定安装详细信息。
    
- 如果MAPIFORM_INSTALL_OVERWRITEONCONFLICT，则同一邮件类之前的任何窗体都将被替换为正在安装的窗体。 否则，表单安装将与当前表单说明（如果存在）合并。
    
- 如果MAPI_DIALOG，MAPIFORM_INSTALL_OVERWRITEONCONFLICT忽略。
    
- 标志集MAPIFORM_INSTALL_OVERWRITEONCONFLICT，意味着将完成合并。 将安装表单说明中当前不存在的 .cfg 文件中的任何新平台，并且不会发生其他更改。
    
- 如果MAPI_UNICODE，则表单配置文件的路径为 Unicode 字符串。 
    
如果 **InstallForm** 返回 MAPI_E_EXTENDED_ERROR，客户端应调用 [IMAPIFormContainer：：GetLastError，](imapiformcontainer-getlasterror.md)并且应检查返回的 [MAPIERROR](mapierror.md)结构以确定引发错误的条件。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|FormContainerDlg.cpp  <br/> |CFormContainerDlg：：OnInstallForm  <br/> |MFCMAPI 使用 **IMAPIFormContainer：：InstallForm** 方法在表单容器中安装表单。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[IMAPIFormContainer : IUnknown](imapiformcontaineriunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

