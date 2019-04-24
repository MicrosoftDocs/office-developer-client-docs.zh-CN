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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309735"
---
# <a name="imsproviderspoolerlogon"></a>IMSProvider::SpoolerLogon

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将 MAPI 后台处理程序记录到邮件存储区。
  
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
  
> 实时指向邮件存储区的 MAPI 支持对象的指针。
    
 _ulUIParam_
  
> 实时此方法显示的任何对话框或窗口的父窗口的句柄。 
    
 _lpszProfileName_
  
> 实时指向包含要用于 MAPI 后台处理程序登录的配置文件的名称的字符串的指针。 此字符串可以显示在对话框中, 将其写出到日志文件中, 或简单地忽略。 如果在_ulFlags_参数中设置了 MAPI_UNICODE 标志, 则它必须采用 Unicode 格式。 
    
 _cbEntryID_
  
> 实时由_lpEntryID_参数指向的条目标识符的大小 (以字节为单位)。 
    
 _lpEntryID_
  
> 实时指向邮件存储区的条目标识符的指针。 在_lpEntryID_参数中传递 NULL 表示尚未选择邮件存储, 并且可以显示允许用户选择邮件存储的对话框。 
    
 _ulFlags_
  
> 实时用于控制登录执行方式的标志的位掩码。 可以设置以下标志:
    
MAPI_DEFERRED_ERRORS 
  
> 即使基础对象对调用实现不可用, 也允许该调用成功。 如果该对象不可用, 则对该对象的后续调用可能会引发错误。
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE, 则字符串将采用 ANSI 格式。
    
MDB_NO_DIALOG 
  
> 阻止显示登录对话框。 如果设置了此标志, 如果登录不成功, 则返回错误值 MAPI_E_LOGON_FAILED。 如果未设置此标志, 则邮件存储提供程序可以提示用户更正名称或密码、插入磁盘或执行与存储建立连接所需的其他操作。
    
MDB_WRITE 
  
> 请求读取/写入权限。
    
 _lpInterface_
  
> 实时指向要登录到的邮件存储区的接口标识符 (IID) 的指针。 传递 NULL 表示将返回邮件存储 ([IMsgStore](imsgstoreimapiprop.md)) 的 MAPI 接口。 也可以将_lpInterface_参数设置为邮件存储区的相应接口的标识符 (例如 IID_IUnknown 或 IID_IMAPIProp)。 
    
 _cbSpoolSecurity_
  
> 实时一个指针, 指向_lppbSpoolSecurity_参数中的验证数据的大小 (以字节为单位)。 
    
 _lpbSpoolSecurity_
  
> 实时指向指向验证数据的指针的指针。 **SpoolerLogon**方法使用此数据, 通过使用[IMSProvider:: Logon](imsprovider-logon.md)方法将 MAPI 后台处理程序记录在与之前登录的邮件存储提供程序相同的存储中。 
    
 _lppMAPIError_
  
> 排除指向包含错误的版本、组件和上下文信息的返回的[MAPIERROR](mapierror.md)结构的指针 (如果有)。 如果没有要返回的**MAPIERROR**结构, 则可以将_lppMAPIError_参数设置为 NULL。 
    
 _lppMSLogon_
  
> 排除指向邮件存储区登录对象的指针, MAPI 将登录到该对象。
    
 _lppMDB_
  
> 排除指向指向要登录到的 MAPI 后台处理程序和客户端应用程序的邮件存储对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_UNCONFIGURED 
  
> 配置文件中包含的信息不足, 无法完成登录。 返回此值时, MAPI 会调用邮件存储提供程序的邮件服务入口点函数。
    
MAPI_W_ERRORS_RETURNED 
  
> 调用成功, 但邮件存储区提供程序有可用的错误信息。 返回此警告时, 应以成功的方式处理该调用。 若要测试此警告, 请使用**HR_FAILED**宏。 有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。 若要从提供程序获取错误消息, 请调用[IMAPISession:: GetLastError](imapisession-getlasterror.md)方法。 
    
## <a name="remarks"></a>注解

MAPI 后台处理程序调用**IMSProvider:: SpoolerLogon**方法以登录到邮件存储区。 在登录期间和之后, MAPI 后台处理程序应使用_lppMDB_参数中的邮件存储提供程序返回的邮件存储对象对象。 
  
为了与[IMSProvider:: Logon](imsprovider-logon.md)方法保持一致, 提供程序还会在_lppMSLogon_参数中返回邮件存储登录对象。 store 对象和 logon 对象的使用与通常的存储登录相同;登录对象和 store 对象之间应存在一对一的对应关系, 这样, 这些对象就像是一个公开两个接口的对象一样。 这两个对象一起创建并一起释放。 
  
存储提供程序应在内部标记返回的邮件存储对象, 以指示 MAPI 后台处理程序正在使用该存储区。 此 store 对象的某些方法的行为与向客户端应用程序提供的邮件存储对象的行为不同。 保持此内部标记是触发特定于 MAPI 后台处理程序的行为的最常见方法。
  
## <a name="see-also"></a>另请参阅



[IMSProvider::Logon](imsprovider-logon.md)
  
[MAPIERROR](mapierror.md)
  
[IMSProvider : IUnknown](imsprovideriunknown.md)

