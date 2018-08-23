---
title: IMSProviderSpoolerLogon
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSProvider.SpoolerLogon
api_type:
- COM
ms.assetid: 79d5af23-efad-4013-a330-56babfb2bb0f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 56c025713b0cc2b41a4bf4463f48f8d7c3d2124b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586415"
---
# <a name="imsproviderspoolerlogon"></a>IMSProvider::SpoolerLogon

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
记录到的消息存储 MAPI 后台处理程序。
  
```cpp
HRESULT SpoolerLogon(
  LPMAPISUP lpMAPISup,
  ULONG_PTR ulUIParam,
  LPSTR lpszProfileName,
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulFlags,
  LPCIID lpInterface,
  ULONG cbSpoolSecurity,
  LPBYTE lpbSpoolSecurity,
  LPMAPIERROR FAR * lppMAPIError,
  LPMSLOGON FAR * lppMSLogon,
  LPMDB FAR * lppMDB     
);
```

## <a name="parameters"></a>参数

 _lpMAPISup_
  
> [in]一个指向 MAPI 支持的消息存储对象。
    
 _ulUIParam_
  
> [in]该方法显示的任何对话框或窗口的父窗口的句柄。 
    
 _lpszProfileName_
  
> [in]一个指向一个字符串，包含要用于 MAPI 后台处理程序登录的配置文件的名称。 可以显示在对话框中，写入日志文件，或只忽略此字符串。 如果_ulFlags_参数中设置 MAPI_UNICODE 标志，它必须是以 Unicode 格式。 
    
 _cbEntryID_
  
> [in]以字节为单位_lpEntryID_参数指向的项标识符的大小。 
    
 _lpEntryID_
  
> [in]指向消息存储库的项标识符的指针。 _LpEntryID_参数中传递 NULL 指示尚未选择的消息存储，并且可以提供让用户能够选择的消息存储的对话框。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何执行登录。 可以设置以下标志：
    
MAPI_DEFERRED_ERRORS 
  
> 若要成功执行，即使基础对象不可用的呼叫的实现，即允许该呼叫。 如果对象不可用，对对象的后续调用可能会引发一个错误。
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 的字符串是以 ANSI 格式。
    
MDB_NO_DIALOG 
  
> 阻止登录对话框的显示。 如果设置此标志，如果登录失败，则返回错误值 MAPI_E_LOGON_FAILED。 如果未设置此标志，消息存储提供程序可以提示用户正确的名称或密码，插入磁盘，或执行其他操作所需建立连接到存储区。
    
MDB_WRITE 
  
> 请求读/写权限。
    
 _lpInterface_
  
> [in]指向要登录到的邮件存储区的接口标识符 (IID) 的指针。 传递 NULL 指示返回的消息存储 ([IMsgStore](imsgstoreimapiprop.md)) 的 MAPI 界面。 _LpInterface_参数还可以设置为消息存储 （例如 IID_IUnknown 或 IID_IMAPIProp） 的适当的接口的标识符。 
    
 _cbSpoolSecurity_
  
> [in]指向的大小，以字节为单位_lppbSpoolSecurity_参数中的验证数据的指针。 
    
 _lpbSpoolSecurity_
  
> [in]指向验证数据的指针的指针。 **SpoolerLogon**方法使用此数据之前使用[IMSProvider::Logon](imsprovider-logon.md)方法登录到的消息存储提供程序以登录到同一个存储 MAPI 后台处理程序。 
    
 _lppMAPIError_
  
> [输出]指向返回[MAPIERROR](mapierror.md)结构，如果有，其中包含的错误的版本、 组件及上下文信息的指针的指针。 如果不没有返回任何**MAPIERROR**结构， _lppMAPIError_参数可以设置为 NULL。 
    
 _lppMSLogon_
  
> [输出]指向该指针指向邮件存储 MAPI 登录到的登录对象。
    
 _lppMDB_
  
> [输出]指向该指针指向邮件存储 MAPI 后台处理程序和客户端应用程序登录到的对象。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_UNCONFIGURED 
  
> 配置文件不包含登录后，若要完成的足够信息。 返回此值时，MAPI 调用的消息存储提供程序的消息服务入口点函数。
    
MAPI_W_ERRORS_RETURNED 
  
> 调用成功，但消息存储提供程序已经可用的错误信息。 返回此警告时，应处理呼叫为成功。 若要测试此警告，请使用**HR_FAILED**宏。 有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。 要从提供程序获取错误的信息，请调用[IMAPISession::GetLastError](imapisession-getlasterror.md)方法。 
    
## <a name="remarks"></a>注解

MAPI 后台处理程序调用**IMSProvider::SpoolerLogon**方法来登录到的消息存储。 MAPI 后台处理程序应使用期间和之后登录_lppMDB_参数中的消息存储提供程序返回的消息存储对象。 
  
对于与[IMSProvider::Logon](imsprovider-logon.md)方法保持一致，提供程序还_lppMSLogon_参数中返回的消息存储登录对象。 使用的存储对象和登录对象是相同的常用存储登录;应一一对应登录对象之间的存储对象，以便对象就像它们是公开两个接口的一个对象。 两个对象一起创建组合在一起和释放。 
  
存储提供程序应将返回的消息存储对象，以指示存储正在使用 MAPI 后台处理程序内部标记。 一些用于此存储对象的方法的行为不同比消息存储提供给客户端应用程序的对象。 保留此内部标志是最常见的触发特定于 MAPI 后台处理程序的行为方式。
  
## <a name="see-also"></a>另请参阅



[IMSProvider::Logon](imsprovider-logon.md)
  
[MAPIERROR](mapierror.md)
  
[IMSProvider : IUnknown](imsprovideriunknown.md)

