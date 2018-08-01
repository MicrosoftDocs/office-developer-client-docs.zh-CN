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
ms.openlocfilehash: 7566bb075c2ef9903b5a376fd90f209c8683c31e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776003"
---
# <a name="iprofadminadminservices"></a>IProfAdmin::AdminServices

  
  
**适用于**： Outlook 
  
提供对邮件服务管理对象的更改配置文件中的消息服务的访问。
  
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
  
> [in]一个指向要修改配置文件的名称。 _LpszProfileName_参数不能为 NULL。 
    
 _lpszPassword_
  
> [in]始终为 NULL。 
    
 _ulUIParam_
  
> [in]任何对话框的父窗口或该方法显示的窗口的句柄。
    
 _ulFlags_
  
> [in]位掩码的标志控制消息服务管理对象检索的。 可以设置以下标志：
    
MAPI_DIALOG 
  
> 启用的用户界面的显示。 
    
MAPI_UNICODE 
  
> 配置文件名称为 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，名称为 ANSI 格式。
    
 _lppServiceAdmin_
  
> [输出]指向与邮件服务管理对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回消息服务管理对象。
    
MAPI_E_LOGON_FAILED 
  
> 指定的配置文件不存在，或密码不正确，无法向用户请求正确的密码，因为 MAPI_DIALOG 未设置_ulFlags_中显示一个对话框。
    
MAPI_E_USER_CANCEL 
  
> 用户取消操作，通常通过单击对话框中的**取消**按钮。 
    
## <a name="remarks"></a>说明

**IProfAdmin::AdminServices**方法提供对邮件服务管理对象的配置更改配置文件中的消息服务的访问。 
  
 _LpszPassword_参数必须为空或为零长度字符串的指针。 
  
## <a name="notes-to-callers"></a>给调用方的说明

尽管您可以通过调用此方法或[IMAPISession::AdminServices](imapisession-adminservices.md)检索[IMsgServiceAdmin](imsgserviceadminiunknown.md)指针，调用**IProfAdmin::AdminServices** ，如果您具有严格配置客户端，并提供任何消息功能。 **IProfAdmin::AdminServices**不创建会话对象，并且未加载任何服务提供商，其增强了性能。 
  
不能使用**IProfAdmin::AdminServices**创建配置文件。 因此，您必须在_lpszProfileName_指定现有的有效的配置文件。 如果指定的配置文件不存在，则**IProfAdmin::AdminServices**返回 MAPI_E_LOGON_FAILED。 
  
配置文件的名称的长度最多为 64 个字符，并可以包含下列字符：
  
- 所有字母数字字符，包括重音字符和下划线字符。 
    
- 嵌入的空格，但不是前导或尾随空格。
    
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIProfileFunctions.cpp  <br/> | HrAddServiceToProfile  <br/> |MFCMAPI 使用**IProfAdmin::AdminServices**方法打开选定的配置文件添加服务消息服务管理对象。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPISession::AdminServices](imapisession-adminservices.md)
  
[IProfAdmin : IUnknown](iprofadminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

