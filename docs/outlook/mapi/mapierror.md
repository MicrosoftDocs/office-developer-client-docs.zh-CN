---
title: MAPIERROR
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MAPIERROR
api_type:
- COM
ms.assetid: e04c2228-aa0a-4958-b5b2-6467e93ab613
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 682e75c4e0a2f60dbd46a13b0b737ca4a8e18f3d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345773"
---
# <a name="mapierror"></a>MAPIERROR

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供有关错误的详细信息, 通常由操作系统、MAPI 或服务提供程序生成。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
```cpp
typedef struct _MAPIERROR
{
  ULONG ulVersion;
  LPSTR lpszError;
  LPSTR lpszComponent;
  ULONG ulLowLevelError;
  ULONG ulContext;
} MAPIERROR, FAR * LPMAPIERROR;

```

## <a name="members"></a>Members

 **ulVersion**
  
> 结构的版本号。 **ulVersion**成员用于将来的扩展, 并且应设置为 MAPI_ERROR_VERSION, 当前定义为零。 
    
 **lpszError**
  
> 指向描述错误的字符串的指针。 如果使用此结构的方法的_ulFlags_参数设置为 MAPI_UNICODE, 则此字符串将采用 Unicode 格式。 
    
 **lpszComponent**
  
> 指向描述生成错误的组件的字符串的指针。 如果使用此结构的方法的_ulFlags_参数设置为 MAPI_UNICODE, 则此字符串将采用 Unicode 格式。 
    
 **ulLowLevelError**
  
> 仅当要返回的错误为低级别时使用的低级错误值。
    
 **ulContext**
  
> 表示组件中的位置的值, **lpszComponent**成员指向标识错误发生位置的位置。 
    
## <a name="remarks"></a>注解

**MAPIERROR**结构用于描述错误消息。 客户端和服务提供程序在[IMAPIProp:: GetLastError](imapiprop-getlasterror.md)方法的_lppMAPIError_参数中传递指向**MAPIERROR**结构的指针。 **GetLastError**返回有关对象上已发生的前一个错误的信息。 **GetLastError**的调用方通过调用[MAPIFreeBuffer](mapifreebuffer.md)来释放**MAPIERROR**结构的内存。
  
**lpszComponent**成员可用于映射组件的帮助文件 (如果存在)。 服务提供程序应将组件字符串的大小限制为30个字符, 以便可以轻松地将其显示在对话框中。 **ulContext**成员还可用于引用常见错误的联机帮助主题。 
  
由于服务提供程序不需要提供详细的错误信息, 因此客户端不应期望返回的**MAPIERROR**结构的任何成员包含有效数据。 但是, 至少 MAPI 中强烈建议提供程序在**lpszComponent**和**ulContext**成员中指定信息。 
  
有关 MAPI 中的错误处理的详细信息, 请参阅[错误处理](error-handling-in-mapi.md)。
  
## <a name="see-also"></a>另请参阅



[IABLogon::GetLastError](iablogon-getlasterror.md)
  
[IABProvider::Logon](iabprovider-logon.md)
  
[IMAPIControl::GetLastError](imapicontrol-getlasterror.md)
  
[IMAPIProp::GetLastError](imapiprop-getlasterror.md)
  
[IMAPISession::GetLastError](imapisession-getlasterror.md)
  
[IMAPISupport::GetLastError](imapisupport-getlasterror.md)
  
[IMAPISupport::OpenAddressBook](imapisupport-openaddressbook.md)
  
[IMAPISession::OpenAddressBook](imapisession-openaddressbook.md)
  
[IMAPITable::GetLastError](imapitable-getlasterror.md)
  
[IMsgServiceAdmin::GetLastError](imsgserviceadmin-getlasterror.md)
  
[IMSLogon::GetLastError](imslogon-getlasterror.md)
  
[IMSProvider::Logon](imsprovider-logon.md)
  
[IProfAdmin::GetLastError](iprofadmin-getlasterror.md)
  
[IProviderAdmin::GetLastError](iprovideradmin-getlasterror.md)


[MAPI 结构](mapi-structures.md)

