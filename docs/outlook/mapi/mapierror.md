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
ms.openlocfilehash: d0ddff638e26940ea74932a8a491455f67cc8dd8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776358"
---
# <a name="mapierror"></a>MAPIERROR

  
  
**适用于**： Outlook 
  
提供有关出错，通常生成的操作系统、 MAPI 或服务提供商的详细的信息。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
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
  
> 结构的版本号。 **UlVersion**成员使用以供将来扩展，并且应设置为 MAPI_ERROR_VERSION，当前定义为零。 
    
 **lpszError**
  
> 指向描述错误字符串。 如果使用此结构方法_ulFlags_参数设置为 MAPI_UNICODE，此字符串将 Unicode 格式。 
    
 **lpszComponent**
  
> 指向描述生成错误的组件的字符串。 如果使用此结构方法_ulFlags_参数设置为 MAPI_UNICODE，此字符串将 Unicode 格式。 
    
 **ulLowLevelError**
  
> 要返回的错误是低级别时才使用的低级错误值。
    
 **ulContext**
  
> 值，该值表示的组件中的位置所指的标识发生错误的**lpszComponent**成员。 
    
## <a name="remarks"></a>说明

**MAPIERROR**结构用于描述错误信息。 客户端和服务提供商到**MAPIERROR**结构[IMAPIProp::GetLastError](imapiprop-getlasterror.md)方法的_lppMAPIError_参数中传递一个指针。 **GetLastError**返回有关以前对对象发生的错误的信息。 呼叫者的**GetLastError**通过调用[MAPIFreeBuffer](mapifreebuffer.md)释放**MAPIERROR**结构的内存。
  
可以使用**lpszComponent**成员映射组件的帮助文件，如果存在。 服务提供商应限制组件字符串 30 个字符的大小，以便它可以轻松地显示在对话框中。 **UlContext**成员还可用于引用常见错误的联机帮助主题。 
  
服务提供商不需要提供详细的错误信息，因为客户端不应期望的任何返回以包含有效数据**MAPIERROR**结构的成员。 但是，在最小 MAPI 强烈建议提供程序，在成员**lpszComponent**和**ulContext**指定信息。 
  
有关 MAPI 中的错误处理的详细信息，请参阅[错误处理](error-handling-in-mapi.md)。
  
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

