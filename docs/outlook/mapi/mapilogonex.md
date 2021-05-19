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
ms.openlocfilehash: 9f2ec8f0ec00f7314982e9b112415f69901c358c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424117"
---
# <a name="mapilogonex"></a>MAPILogonEx

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将客户端应用程序记录到与邮件系统的会话。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapix.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
   
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
  
> [in]对登录对话框模式化窗口的句柄。 如果在调用过程中未显示任何对话框，  _则忽略 ulUIParam_ 参数。 此参数可以是零。 
    
 _lpszProfileName_
  
> [in]指向包含用户登录时使用的配置文件名称的字符串的指针。 此字符串长度为 64 个字符限制。
    
 _lpszPassword_
  
> [in]指向包含配置文件密码的字符串的指针。 _lpszPassword_ 参数必须为 NULL。 
    
 _flFlags_
  
> [in]用于控制如何执行登录的标志的位掩码。 可以设置以下标志：
    
MAPI_ALLOW_OTHERS 
  
> 应返回共享会话，这将允许稍后的客户端获取会话，而不提供任何用户凭据。 
    
MAPI_BG_SESSION
  
> 登录到会话并在后台运行任何操作。 通常，如果客户端打算在后台线程上或在单独的进程中以对前台线程不突起的方式进行处理，它应调用 MAPI_BG_SESSION 标志。 客户端应用程序（如索引引擎或打开个人文件夹文件 (PST) 进行后台类型访问）是使用 MAPI_BG_SESSION 的一些示例。MAPILogonEx。
    
MAPI_EXPLICIT_PROFILE 
  
> 不应使用默认配置文件，并且应该要求用户提供配置文件。 
    
MAPI_EXTENDED 
  
> 使用扩展功能登录。 应始终设置此标志。
    
MAPI_FORCE_DOWNLOAD 
  
> 在返回之前，应尝试下载用户的所有邮件。 如果未MAPI_FORCE_DOWNLOAD，可以在调用 MAPILogonEx 后在后台下载邮件。 
    
MAPI_LOGON_UI 
  
> 应显示一个对话框，以提示用户输入登录信息（如果需要）。 如果未MAPI_LOGON_UI，则调用客户端不显示登录对话框，如果用户未登录，则返回错误值。
    
MAPI_NEW_SESSION 
  
> 应尝试创建新的 MAPI 会话，而不是获取共享会话。 如果未MAPI_NEW_SESSION，MAPILogonEx 将使用现有的共享会话，即使  _lpszprofileName_ 参数不为 NULL。 
    
MAPI_NO_MAIL 
  
> MAPI 不应通知 MAPI 后台处理程序会话是否存在。 结果是会话无法发送或接收邮件，通过紧密耦合的存储和传输对除外。 如果呼叫客户端充当代理、必须完成配置工作或客户端正在浏览可用邮件存储，则呼叫客户端将设置此标志。 
    
MAPI_NT_SERVICE 
  
> 调用方作为服务Windows运行。 未作为服务运行的Windows不应设置此标志;作为服务运行的调用方必须设置此标志。 
    
MAPI_SERVICE_UI_ALWAYS 
  
> MAPILogonEx 应显示配置文件中每个邮件服务的配置对话框。 对话框显示在已选择配置文件之后，但在任何邮件服务登录之前。 用于登录的 MAPI 常见对话框还包含一个请求相同操作的复选框。 
    
MAPI_TIMEOUT_SHORT 
  
> 如果阻止的时间超过几秒钟，登录应该会失败。 
    
MAPI_UNICODE 
  
> 传入字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。 
    
MAPI_USE_DEFAULT 
  
> 邮件子系统应该将默认配置文件的配置文件名称替换为  _lpszProfileName_ 参数。 除非  _lpszProfileName_ 为 NULL 或空，否则忽略 MAPI_EXPLICIT_PROFILE 标志。 
    
 _lppSession_
  
> [out]指向指向 MAPI 会话接口的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 登录成功。
    
MAPI_E_LOGON_FAILED 
  
> 登录失败，原因是 MAPILogonEx 的一个或多个参数无效或已打开的会话过多。
    
MAPI_E_TIMEOUT 
  
> MAPI 通过互斥法序列化所有登出。 如果设置了互斥MAPI_TIMEOUT_SHORT另一个线程持有互斥标记，则返回此状态。 
    
MAPI_E_USER_CANCEL 
  
> 用户通常通过单击对话框中的"取消" **按钮来取消** 操作。 
    
## <a name="remarks"></a>备注

MAPI 客户端应用程序调用 MAPILogonEx 函数以登录到与邮件系统的会话。 传入 MAPI 调用以及从 MAPI 调用返回和返回的所有字符串均以 null 结束，必须在调用客户端或提供程序的操作系统的当前字符集或代码页中指定。
  
如果之前存在一个调用 MapiLogonEx 且设置了 MAPI_ALLOW_OTHERS 标志的现有会话，并且未设置 MAPI_NEW_SESSION，则  _lpszProfileName_ 参数将被忽略。 如果  _lpszProfileName_ 参数为 NULL 或指向空字符串，  _并且 flFlags_ 参数包含 MAPI_LOGON_UI 标志，则 MAPILogonEx 函数将生成一个登录对话框，其中包含配置文件名称的空字段。 
  
登录到特定配置文件时，除了配置文件名称之外，客户端还应MAPI_NEW_SESSION标志传递到 MAPILogonEx。 否则，如果另一个客户端通过登录 MAPI_ALLOW_OTHERS 建立了共享会话，则客户端将登录到共享会话，而不是所请求的配置文件。 
  
当  _lpszProfileName_ 为 NULL 或为空时，MAPI_EXPLICIT_PROFILE标志不会导致使用默认配置文件名称，除非 MAPI_USE_DEFAULT标志存在。 
  
当MAPI_NO_MAIL MAPI 后台处理程序时，MAPI_NO_MAIL 标记具有多个影响：：
  
- 在此会话期间，MAPI 后台处理程序无法发送或传递任何消息。 只有紧密耦合的存储和传输提供程序才能发送和接收邮件。 
    
- 基于服务器的存储区可能仍发送或传递邮件。 
    
- 任何挂钩提供程序不处理由基于服务器的存储发送或传递的邮件。 
    
- 传输的"每邮件"和"每收件人"选项不可用。 
    
- 状态表不包含传输提供程序的条目，并且依赖于状态对象的任何传输功能 (配置) 不可用。 
    
- 状态表中的邮件后台处理程序行包含STATUS_FAILURE值。 
    
- 允许使用Gybacked登录，但这些登录不会导致以前的登录接收状态对象更新。 
    
服务应始终使用 MAPI_NO_MAIL 登录。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIObjects.cpp  <br/> |CMapiObjects：：MAPILogonEx  <br/> |MFCMAPI 使用 MAPILogonEx 方法登录到 MAPI。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md)
  
[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

