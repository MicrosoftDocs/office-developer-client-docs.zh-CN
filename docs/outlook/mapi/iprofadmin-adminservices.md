---
title: IProfAdminAdminServices
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.AdminServices
api_type:
- COM
ms.assetid: 87235fd2-6527-41a1-98ba-b951632a1c81
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2c504f98655e35af62810dd428e8e04878a36dec
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422080"
---
# <a name="iprofadminadminservices"></a>IProfAdmin::AdminServices

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供对邮件服务管理对象的访问权限，以对配置文件中的邮件服务进行更改。
  
```cpp
HRESULT AdminServices(
  LPSTR lpszProfileName,
  LPSTR lpszPassword,
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPSERVICEADMIN FAR * lppServiceAdmin
);
```

## <a name="parameters"></a>参数

 _lpszProfileName_
  
> [in]指向要修改的配置文件的名称的指针。 _lpszProfileName_ 参数不能为 NULL。 
    
 _lpszPassword_
  
> [in]始终为 NULL。 
    
 _ulUIParam_
  
> [in]此方法显示的任何对话框或窗口的父窗口的句柄。
    
 _ulFlags_
  
> [in]控制邮件服务管理对象检索的标志的位掩码。 可以设置以下标志：
    
MAPI_DIALOG 
  
> 启用用户界面的显示。 
    
MAPI_UNICODE 
  
> 配置文件名称采用 Unicode 格式。 如果未MAPI_UNICODE，则名称采用 ANSI 格式。
    
 _lppServiceAdmin_
  
> [out]指向指向邮件服务管理对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回邮件服务管理对象。
    
MAPI_E_LOGON_FAILED 
  
> 指定的配置文件不存在，或者密码错误，并且无法向用户显示对话框来请求正确的密码，因为 MAPI_DIALOG  _ulFlags_ 中未设置。
    
MAPI_E_USER_CANCEL 
  
> 用户通常通过单击对话框中的"取消" **按钮来取消** 操作。 
    
## <a name="remarks"></a>备注

**IProfAdmin：：AdminServices** 方法提供对邮件服务管理对象的访问权限，以对配置文件中的邮件服务进行配置更改。 
  
 _lpszPassword_ 参数必须为 NULL 或指向零长度字符串的指针。 
  
## <a name="notes-to-callers"></a>给调用方的说明

尽管可以通过调用此方法或 [IMAPISession：：AdminServices](imapisession-adminservices.md)来检索 [IMsgServiceAdmin](imsgserviceadminiunknown.md)指针，但如果严格具有配置客户端并且未提供消息功能，请调用 **IProfAdmin：：AdminServices。** **IProfAdmin：：AdminServices** 不会创建会话对象，也不加载任何服务提供程序，这将提高性能。 
  
不能使用 **IProfAdmin：：AdminServices** 创建配置文件。 因此，您必须在  _lpszProfileName_ 中指定现有的有效配置文件。 如果指定的配置文件不存在， **则 IProfAdmin：：AdminServices** 将返回MAPI_E_LOGON_FAILED。 
  
配置文件的名称长度最多为 64 个字符，可以包含下列字符：
  
- 所有字母数字字符，包括重音字符和下划线字符。 
    
- 嵌入空格，但不包括前导或尾随空格。
    
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIProfileFunctions.cpp  <br/> | HrAddServiceToProfile  <br/> |MFCMAPI 使用 **IProfAdmin：：AdminServices** 方法打开所选配置文件的邮件服务管理对象以添加服务。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPISession::AdminServices](imapisession-adminservices.md)
  
[IProfAdmin : IUnknown](iprofadminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

