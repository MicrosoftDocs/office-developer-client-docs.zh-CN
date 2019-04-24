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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351644"
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
  
> 实时此方法显示的任何对话框或窗口的父窗口的句柄。 除非客户端应用程序在_ulFlags_参数中设置了 MAPI_DIALOG 标志, 否则将忽略_ulUIParam_参数。 如果不同时传递 MAPI_DIALOG, 则_ulUIParam_参数可以为 NULL。 
    
 _ulFlags_
  
> 实时用于控制表单安装的标志的位掩码。 可以设置以下标志:
    
MAPI_DIALOG 
  
> 显示一个对话框, 以提供进度信息或提示用户详细信息。 如果未设置此标志, 则不会显示任何对话框。
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。
    
MAPIFORM_INSTALL_OVERWRITEONCONFLICT 
  
> 如果已存在另一个处理此表单处理的邮件类的窗体, 请将现有表单替换为此表单。 如果还存在 MAPI_DIALOG 标志, 则忽略此标志。 
    
 _szCfgPathName_
  
> 实时表单的配置文件的路径。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_EXTENDED_ERROR 
  
> 发生了实现错误。 若要获取与错误相关联的[MAPIERROR](mapierror.md)结构, 请调用[IMAPIFormContainer:: GetLastError](imapiformcontainer-getlasterror.md)方法。 
    
MAPI_E_USER_CANCEL 
  
> 用户取消了窗体的安装, 通常通过单击对话框中的 "**取消**" 按钮。 
    
## <a name="notes-to-implementers"></a>针对实现者的说明

表单库提供程序应填写**MAPIERROR**结构, 如果出现以下任一情况, 则返回 MAPI_E_EXTENDED_ERROR: 
  
- 找不到配置文件。
    
- 配置文件不可读。
    
- 配置文件无效。
    
## <a name="notes-to-callers"></a>给调用方的说明

客户端应用程序调用**IMAPIFormContainer:: InstallForm**方法将表单安装到特定的表单容器中。 _szCfgPathName_参数必须包含表单配置文件的路径 (即, 具有用于描述表单及其实现的扩展名为. cfg 的文件)。 _ulFlags_参数中的标志指定以下内容: 
  
- 如果设置了 MAPI_DIALOG 标志, 则显示一个用户界面, 使正在安装该表单的用户可以指定安装详细信息。
    
- 如果设置了 MAPIFORM_INSTALL_OVERWRITEONCONFLICT 标志, 则同一邮件类的任何以前的窗体将替换为正在安装的窗体。 否则, 将使用当前的表单说明 (如果存在) 合并表单安装。
    
- 如果设置了 MAPI_DIALOG, 则将忽略 MAPIFORM_INSTALL_OVERWRITEONCONFLICT。
    
- 标记集中缺少 MAPIFORM_INSTALL_OVERWRITEONCONFLICT 意味着将完成合并。 将会安装在表单说明中当前未出现的 cfg 文件中的任何新平台, 并且不会进行其他更改。
    
- 如果设置了 MAPI_UNICODE 标志, 则表单配置文件的路径为 UNICODE 字符串。 
    
客户端应调用[IMAPIFormContainer:: GetLastError](imapiformcontainer-getlasterror.md) (如果**InstallForm**返回 MAPI_E_EXTENDED_ERROR), 并应检查返回的[MAPIERROR](mapierror.md)结构以确定引发错误的条件。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|FormContainerDlg  <br/> |CFormContainerDlg:: OnInstallForm  <br/> |MFCMAPI 使用**IMAPIFormContainer:: InstallForm**方法在表单容器中安装表单。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[IMAPIFormContainer : IUnknown](imapiformcontaineriunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

