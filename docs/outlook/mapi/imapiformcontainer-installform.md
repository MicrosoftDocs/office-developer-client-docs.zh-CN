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
ms.openlocfilehash: d329d3a14b6026d0bd62df9feba6ccff251e4151
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775393"
---
# <a name="imapiformcontainerinstallform"></a>IMAPIFormContainer::InstallForm

  
  
**适用于**： Outlook 
  
将窗体安装到表单库。
  
```cpp
HRESULT InstallForm(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPCSTR szCfgPathName
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]任何对话框的父窗口或该方法显示的窗口句柄。 除非客户端应用程序中的_ulFlags_参数设置 MAPI_DIALOG 标志，则将忽略该_ulUIParam_参数。 如果还未传递 MAPI_DIALOG _ulUIParam_参数可以是 NULL。 
    
 _ulFlags_
  
> [in]位掩码的标志的控件的窗体的安装。 可以设置以下标志：
    
MAPI_DIALOG 
  
> 显示一个对话框，以提供进度信息或提示用户输入的详细信息。 如果未设置此标志，则不显示任何对话框。
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。
    
MAPIFORM_INSTALL_OVERWRITEONCONFLICT 
  
> 如果另一个窗体已存在的邮件类处理由此窗体的句柄，请使用此替换现有的表单。 如果 MAPI_DIALOG 标志还存在，则忽略此标志。 
    
 _szCfgPathName_
  
> [in]窗体的配置文件的路径。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_EXTENDED_ERROR 
  
> 实现时出错。 要获取与错误关联的[MAPIERROR](mapierror.md)结构，请调用[IMAPIFormContainer::GetLastError](imapiformcontainer-getlasterror.md)方法。 
    
MAPI_E_USER_CANCEL 
  
> 用户取消安装的窗体，通常通过单击对话框中的**取消**按钮。 
    
## <a name="notes-to-implementers"></a>针对实施者的注释

窗体库提供程序应填充**MAPIERROR**结构中，并返回 MAPI_E_EXTENDED_ERROR，如果发生以下情况： 
  
- 未找到配置文件。
    
- 配置文件不可读。
    
- 无效的配置文件。
    
## <a name="notes-to-callers"></a>给调用方的说明

客户端应用程序调用**IMAPIFormContainer::InstallForm**方法以安装到特定的窗体容器的窗体。 _SzCfgPathName_参数必须包含窗体配置文件 （即，介绍了窗体和其实现.cfg 扩展名文件） 的路径。 Flags _ulFlags_参数中的指定以下设置： 
  
- 如果设置了 MAPI_DIALOG 标志，将显示用户界面，启用安装时指定安装详细信息窗体的用户。
    
- 如果设置了 MAPIFORM_INSTALL_OVERWRITEONCONFLICT 标志，与正在安装该表单替换同一邮件类的任何以前窗体。 否则，窗体安装合并与当前的窗体说明中，如果存在。
    
- 如果设置 MAPI_DIALOG，则忽略 MAPIFORM_INSTALL_OVERWRITEONCONFLICT。
    
- 在标记不存在 MAPIFORM_INSTALL_OVERWRITEONCONFLICT 设置意味着将完成合并。 将安装任何新平台.cfg 文件中的，不窗体说明中当前存在和任何其他更改，则会发生。
    
- 如果设置了 MAPI_UNICODE 标志，窗体配置文件的路径为 Unicode 字符串。 
    
如果**InstallForm**返回 MAPI_E_EXTENDED_ERROR，并且他们应检查返回的[MAPIERROR](mapierror.md)结构，以确定引发错误条件，客户端应调用[IMAPIFormContainer::GetLastError](imapiformcontainer-getlasterror.md) 。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|FormContainerDlg.cpp  <br/> |CFormContainerDlg::OnInstallForm  <br/> |MFCMAPI 使用**IMAPIFormContainer::InstallForm**方法在窗体容器中安装窗体。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[IMAPIFormContainer : IUnknown](imapiformcontaineriunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

