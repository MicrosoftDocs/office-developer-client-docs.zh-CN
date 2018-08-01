---
title: MAPILogonEx
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPILogonEx
api_type:
- HeaderDef
ms.assetid: 98091e5b-1abd-4814-9c7a-583b420ee11d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 08782fe616fe260388cff8982dfbb09951453a00
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776362"
---
# <a name="mapilogonex"></a>MAPILogonEx

  
  
**适用于**： Outlook 
  
记录到会话的客户端应用程序包含在邮件系统。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapix.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
   
```cpp
HRESULT MAPILogonEx(
  ULONG_PTR ulUIParam,
  LPSTR lpszProfileName,
  LPSTR lpszPassword,
  FLAGS flFlags,
  LPMAPISESSION FAR * lppSession
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]到登录对话框是模式窗体窗口的句柄。 如果在呼叫期间不出现任何对话框，则忽略_ulUIParam_参数。 此参数可以是零。 
    
 _lpszProfileName_
  
> [in]指向一个字符串，包含要在用户登录时使用的配置文件的名称。 此字符串长度为 64 个字符限制。
    
 _lpszPassword_
  
> [in]指向一个字符串，包含配置文件的密码。 _LpszPassword_参数必须为 NULL。 
    
 _flFlags_
  
> [in]用于控制如何执行登录的标志位掩码。 可以设置以下标志：
    
MAPI_ALLOW_OTHERS 
  
> 应返回共享的会话，它允许更高版本的客户端可以获得该会话不需提供任何用户凭据。 
    
MAPI_BG_SESSION
  
> 登录到会话，并在后台运行任何操作。 一般来说，如果打算执行后台线程上或在单独的进程中不到前台线程引人注目的方式处理客户端，它应与 MAPI_BG_SESSION 标志调用。 如索引引擎或打开背景类型访问个人文件夹文件 (PST) 的客户端应用程序是在何处使用 MAPI_BG_SESSION 的一些示例。MAPILogonEx。
    
MAPI_EXPLICIT_PROFILE 
  
> 不应使用默认配置文件，并应要求用户提供一个配置文件。 
    
MAPI_EXTENDED 
  
> 登录与扩展的功能。 此标志应始终设置。
    
MAPI_FORCE_DOWNLOAD 
  
> 尝试应进行返回之前下载的所有用户的邮件。 如果未设置 MAPI_FORCE_DOWNLOAD 标志，则后对 MAPILogonEx 的调用返回，在后台可以下载消息。 
    
MAPI_LOGON_UI 
  
> 应显示一个对话框，提示用户输入登录信息，如果需要。 时未设置 MAPI_LOGON_UI 标志，调用客户端不显示登录对话框，并返回一个错误值，如果用户未登录。
    
MAPI_NEW_SESSION 
  
> 尝试应进行创建一个新的 MAPI 会话，而不是获取共享的会话。 如果未设置 MAPI_NEW_SESSION 标志，MAPILogonEx 使用现有共享的会话，即使_lpszprofileName_参数不是 NULL。 
    
MAPI_NO_MAIL 
  
> MAPI 不应告知该会话的存在 MAPI 后台处理程序。 结果是可以发送或接收除了通过紧密耦合存储和传输对会话中任何消息。 调用客户端设置此标志，如果它充当代理，如果必须完成的配置工作，或者如果客户端浏览可用的邮件存储区。 
    
MAPI_NT_SERVICE 
  
> 呼叫者作为 Windows 服务运行。 呼叫者的一项 Windows 服务不应设置此标志; 如未运行作为服务运行的呼叫者必须设置此标志。 
    
MAPI_SERVICE_UI_ALWAYS 
  
> MAPILogonEx 应显示配置文件中的每个消息服务的配置对话框。 已选中该配置文件，但任何消息之前服务登录后显示的对话框。 登录的 MAPI 常见对话框还包含一个请求相同的操作的复选框。 
    
MAPI_TIMEOUT_SHORT 
  
> 如果多个几秒钟阻止，则应该会失败登录。 
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。 
    
MAPI_USE_DEFAULT 
  
> 邮件子系统应替换为_lpszProfileName_参数的默认配置文件的配置文件名称。 除非_lpszProfileName_为 NULL 或空，则忽略 MAPI_EXPLICIT_PROFILE 标志。 
    
 _lppSession_
  
> [输出]为指向 MAPI 会话接口的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 登录成功。
    
MAPI_E_LOGON_FAILED 
  
> 登录成功，因为一个或多个 MAPILogonEx 的参数无效或因太多的会话打开已。
    
MAPI_E_TIMEOUT 
  
> MAPI 序列化通过互斥体的所有登录。 如果设置了 MAPI_TIMEOUT_SHORT 标志和另一个线程保留互斥体，这将返回。 
    
MAPI_E_USER_CANCEL 
  
> 用户取消操作，通常通过单击对话框中的**取消**按钮。 
    
## <a name="remarks"></a>说明

MAPI 客户端应用程序调用 MAPILogonEx 函数登录到与邮件系统的会话。 所有字符串中传递并返回与 MAPI 调用 null 结尾并且必须指定以当前字符集或代码页的呼叫的客户端或提供程序的操作系统。
  
如果设置了 MAPI_ALLOW_OTHERS 标志调用 MapiLogonEx 现有以前会话和未设置标志 MAPI_NEW_SESSION 忽略_lpszProfileName_参数。 如果_lpszProfileName_参数为 NULL 或空字符串和_flFlags_参数指向包含 MAPI_LOGON_UI 标志，MAPILogonEx 函数将生成具有的配置文件名称的字段为空登录对话框。 
  
在登录到特定配置文件时, 客户端应将传递 MAPI_NEW_SESSION 标志到 MAPILogonEx 除了的配置文件名称。 否则，如果另一个客户端的登录与 MAPI_ALLOW_OTHERS 建立共享的会话，客户端将登录到请求的配置文件而不是将共享会话。 
  
MAPI_EXPLICIT_PROFILE 标志不会导致_lpszProfileName_为 NULL 时要使用的默认配置文件名称或为空，除非也存在 MAPI_USE_DEFAULT 标志。 
  
MAPI_NO_MAIL 标志具有不使用 MAPI 后台处理程序时，会导致以下几种效果：
  
- 可以发送或此会话期间发送 MAPI 后台处理程序的任何消息。 仅紧密耦合的存储和传输提供程序可以发送和邮件传递。 
    
- 基于服务器存储可能仍发送，或将邮件传递。 
    
- 发送或基于服务器存储的邮件将不会执行任何挂接提供商。 
    
- 传输的每封邮件和每个收件人选项不可用。 
    
- 状态表中不包含传输提供程序的条目和依赖于状态对象 （如配置） 在任何传输功能不可用。 
    
- 状态表中的邮件后台处理程序行包含 STATUS_FAILURE 值。 
    
- 允许随附加的登录，但这些登录不会导致一次登录以接收对象的状态更新。 
    
服务应始终使用登录 MAPI_NO_MAIL 标志。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIObjects.cpp  <br/> |CMapiObjects::MAPILogonEx  <br/> |MFCMAPI 使用 MAPILogonEx 方法登录到 MAPI。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md)
  
[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

