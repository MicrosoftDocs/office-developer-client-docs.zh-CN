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
  
将客户端应用程序记录到邮件系统的会话中。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapix  <br/> |
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
  
> 实时指向登录对话框模式的窗口的句柄。 如果在呼叫过程中不显示任何对话框, 则忽略_ulUIParam_参数。 此参数可以为零。 
    
 _lpszProfileName_
  
> 实时指向一个字符串的指针, 该字符串包含要在用户登录时使用的配置文件的名称。 此字符串长度为 64 个字符限制。
    
 _lpszPassword_
  
> 实时指向包含配置文件密码的字符串的指针。 _lpszPassword_参数必须为 NULL。 
    
 _flFlags_
  
> 实时用于控制登录执行方式的标志的位掩码。 可以设置以下标志:
    
MAPI_ALLOW_OTHERS 
  
> 应返回共享会话, 这样以后客户端无需提供任何用户凭据即可获取会话。 
    
MAPI_BG_SESSION
  
> 登录到会话并在后台运行任何操作。 通常情况下, 如果客户端打算在后台线程上或在单独的进程中以与前台线程不引人注目的方式进行处理, 则应使用 MAPI_BG_SESSION 标志进行调用。 用于后台类型访问的客户端应用程序 (如索引引擎或打开个人文件夹文件 (PST)) 是使用 MAPI_BG_SESSION 的一些示例。MAPILogonEx。
    
MAPI_EXPLICIT_PROFILE 
  
> 不应使用默认配置文件, 应要求用户提供配置文件。 
    
MAPI_EXTENDED 
  
> 使用扩展的功能进行登录。 应始终设置此标志。
    
MAPI_FORCE_DOWNLOAD 
  
> 应在返回前尝试下载用户的所有邮件。 如果未设置 MAPI_FORCE_DOWNLOAD 标志, 则在调用 MAPILogonEx 后, 可以在后台下载邮件。 
    
MAPI_LOGON_UI 
  
> 应显示一个对话框, 提示用户输入登录信息 (如果需要)。 如果未设置 MAPI_LOGON_UI 标志, 则调用客户端不会显示登录对话框, 并会在用户未登录时返回一个错误值。
    
MAPI_NEW_SESSION 
  
> 应尝试创建新的 MAPI 会话, 而不是获取共享会话。 如果未设置 MAPI_NEW_SESSION 标志, 则 MAPILogonEx 将使用现有共享会话, 即使_lpszprofileName_参数不为 NULL 也是如此。 
    
MAPI_NO_MAIL 
  
> mapi 不应通知 mapi 后台处理程序存在该会话。 结果是, 不能在会话中发送或接收邮件, 除非通过紧密耦合的存储和传输对。 如果呼叫客户端正在充当代理 (如果必须完成配置工作, 或者客户端正在浏览可用的邮件存储), 则呼叫客户端将设置此标志。 
    
MAPI_NT_SERVICE 
  
> 调用方以 Windows 服务的形式运行。 未作为 Windows 服务运行的调用方不应设置此标志;作为服务运行的调用方必须设置此标志。 
    
MAPI_SERVICE_UI_ALWAYS 
  
> MAPILogonEx 应为配置文件中的每个邮件服务显示一个 "配置" 对话框。 在选择了配置文件之后, 但在任何邮件服务登录之前, 都会显示对话框。 用于登录的 MAPI 通用对话框还包含一个请求同一操作的复选框。 
    
MAPI_TIMEOUT_SHORT 
  
> 如果被阻止了数秒以上, 则登录应该会失败。 
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。 
    
MAPI_USE_DEFAULT 
  
> 邮件传递子系统应替换_lpszProfileName_参数的默认配置文件的配置文件名称。 除非_lpszProfileName_为 NULL 或为空, 否则将忽略 MAPI_EXPLICIT_PROFILE 标志。 
    
 _lppSession_
  
> 排除指向 MAPI 会话接口的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 登录成功。
    
MAPI_E_LOGON_FAILED 
  
> 登录失败, 可能是因为一个或多个 MAPILogonEx 参数无效, 或者因为已打开的会话过多。
    
MAPI_E_TIMEOUT 
  
> MAPI 通过 mutex 序列化所有登录。 如果设置了 MAPI_TIMEOUT_SHORT 标志, 而另一个线程持有互斥体, 则将返回此设置。 
    
MAPI_E_USER_CANCEL 
  
> 用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。 
    
## <a name="remarks"></a>说明

MAPI 客户端应用程序调用 MAPILogonEx 函数, 以登录到邮件系统的会话。 传入和返回 MAPI 调用的所有字符串都以空值终止, 并且必须在当前的字符集或调用客户端或提供程序的操作系统的 "代码" 页中指定。
  
如果现有的前一个会话已设置 MAPI_ALLOW_OTHERS 标志, 且未设置标志 MAPI_NEW_SESSION, 则将忽略_lpszProfileName_参数。 如果_lpszProfileName_参数为 NULL 或指向一个空字符串, 并且_flFlags_参数包含 MAPI_LOGON_UI 标志, 则 MAPILogonEx 函数将生成一个登录对话框, 其中包含配置文件名称的空字段。 
  
登录到特定配置文件时, 除了配置文件名称之外, 客户端还应将 MAPI_NEW_SESSION 标志传递给 MAPILogonEx。 否则, 如果另一个客户端通过使用 MAPI_ALLOW_OTHERS 登录来建立共享会话, 客户端将登录到共享会话, 而不是所请求的配置文件。 
  
如果_lpszProfileName_为 NULL 或为空, 则 MAPI_EXPLICIT_PROFILE 标志不会导致使用默认配置文件名称, 除非同时也存在 MAPI_USE_DEFAULT 标志。 
  
在不使用 MAPI 后台处理程序的情况下, MAPI_NO_MAIL 标志有几个导致以下影响的效果:
  
- 在此会话期间, MAPI 后台处理程序无法发送或传递任何邮件。 仅紧密耦合的存储和传输提供程序可以发送和传递邮件。 
    
- 基于服务器的存储可能仍在发送或传递邮件。 
    
- 任何挂钩提供程序都不处理由基于服务器的存储区发送或传递的邮件。 
    
- 传输的每个邮件和每个收件人的选项都不可用。 
    
- 状态表不包含传输提供程序的条目, 且依赖于状态对象的任何传输功能 (如配置) 不可用。 
    
- 状态表中的邮件后台打印程序行包含 STATUS_FAILURE 值。 
    
- 允许 Piggybacked 登录, 但这些登录不会导致以前的登录接收状态对象更新。 
    
服务应始终使用 MAPI_NO_MAIL 标志进行登录。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIObjects  <br/> |CMapiObjects:: MAPILogonEx  <br/> |MFCMAPI 使用 MAPILogonEx 方法登录 MAPI。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md)
  
[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

