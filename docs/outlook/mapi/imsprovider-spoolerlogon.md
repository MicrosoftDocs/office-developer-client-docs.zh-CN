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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 794674df38266743cac8c947ec93dc1fcfff438b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430572"
---
# <a name="imsproviderspoolerlogon"></a>IMSProvider::SpoolerLogon

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将 MAPI 后台处理程序记录到邮件存储。
  
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
  
> [in]指向邮件存储的 MAPI 支持对象的指针。
    
 _ulUIParam_
  
> [in]该方法显示的任何对话框或窗口的父窗口的句柄。 
    
 _lpszProfileName_
  
> [in]指向包含用于 MAPI 后台处理程序登录的配置文件名称的字符串的指针。 此字符串可以在对话框中显示、写入或日志文件或忽略。 如果在  _ulFlags_ 参数中设置了 MAPI_UNICODE 标志，则它必须采用 Unicode 格式。 
    
 _cbEntryID_
  
> [in]  _lpEntryID_ 参数指向的条目标识符的大小（以字节为单位）。 
    
 _lpEntryID_
  
> [in]指向邮件存储的条目标识符的指针。 在  _lpEntryID_ 参数中传递 NULL 表示尚未选择邮件存储，并且会显示允许用户选择邮件存储的对话框。 
    
 _ulFlags_
  
> [in]控制如何执行登录的标志的位掩码。 可以设置以下标志：
    
MAPI_DEFERRED_ERRORS 
  
> 即使基础对象对调用实现不可用，也允许调用成功。 如果该对象不可用，则对该对象的后续调用可能会引发错误。
    
MAPI_UNICODE 
  
> 传入字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。
    
MDB_NO_DIALOG 
  
> 禁止显示登录对话框。 如果设置此标志，则返回错误MAPI_E_LOGON_FAILED登录不成功时返回。 如果未设置此标志，则邮件存储提供程序可以提示用户更正名称或密码、插入磁盘或执行与存储建立连接所需的其他操作。
    
MDB_WRITE 
  
> 请求读/写权限。
    
 _lpInterface_
  
> [in]指向接口标识符的 (IID) 供邮件存储登录。 传递 NULL 指示返回 [IMsgStore](imsgstoreimapiprop.md) (邮件存储) MAPI 接口。 _还可以将 lpInterface_ 参数设置为邮件存储应用程序的适当接口的标识符 (例如 IID_IUnknown 或 IID_IMAPIProp) 。 
    
 _cbSpoolSecurity_
  
> [in]指向  _lppbSpoolSecurity_ 参数中验证数据的大小（以字节为单位）的指针。 
    
 _lpbSpoolSecurity_
  
> [in]指向验证数据的指针的指针。 **SpoolerLogon** 方法使用此数据通过 [IMSProvider：：Logon](imsprovider-logon.md)方法将 MAPI 后台处理程序记录到之前登录的消息存储提供程序所登录到的同一存储。 
    
 _lppMAPIError_
  
> [out]指向返回的 [MAPIERROR](mapierror.md) 结构的指针（如果有）的指针，其中包含错误的版本、组件和上下文信息。 如果没有要返回的 **MAPIERROR** 结构，可以将 _lppMAPIError_ 参数设置为 NULL。 
    
 _lppMSLogon_
  
> [out]指向指向 MAPI 要登录的消息存储登录对象的指针的指针。
    
 _lppMDB_
  
> [out]指向 MAPI 后台处理程序和客户端应用程序要登录的消息存储对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
MAPI_E_UNCONFIGURED 
  
> 配置文件包含的信息不足，无法完成登录。 返回此值时，MAPI 将调用邮件存储提供程序的邮件服务入口点函数。
    
MAPI_W_ERRORS_RETURNED 
  
> 调用成功，但邮件存储提供程序提供错误信息。 返回此警告时，应成功处理呼叫。 若要测试此警告，请使用 **HR_FAILED** 宏。 有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。 若要从提供程序获取错误信息，请调用 [IMAPISession：：GetLastError](imapisession-getlasterror.md) 方法。 
    
## <a name="remarks"></a>备注

MAPI 后台处理程序调用 **IMSProvider：：SpoolerLogon** 方法以登录到消息存储。 MAPI 后台处理程序应在登录期间和登录后使用邮件存储提供程序在  _lppMDB_ 参数中返回的邮件存储对象。 
  
为了与 [IMSProvider：：Logon](imsprovider-logon.md) 方法保持一致，提供程序还会在  _lppMSLogon_ 参数中返回消息存储登录对象。 存储对象的使用与通常存储登录的登录对象相同;登录对象和存储对象之间应该存在一对一的对应关系，这样对象的行为就就像它们是一个公开两个接口的对象一样。 这两个对象一起创建并释放在一起。 
  
存储提供程序应在内部标记返回的邮件存储对象，以指示 MAPI 后台处理程序正在使用存储。 此存储对象的一些方法的行为不同于提供给客户端应用程序的邮件存储对象的行为。 保留此内部标记是触发特定于 MAPI 后台处理程序的行为的最常见方法。
  
## <a name="see-also"></a>另请参阅



[IMSProvider::Logon](imsprovider-logon.md)
  
[MAPIERROR](mapierror.md)
  
[IMSProvider : IUnknown](imsprovideriunknown.md)

