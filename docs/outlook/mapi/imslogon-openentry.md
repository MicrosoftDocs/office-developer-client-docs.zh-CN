---
title: IMSLogonOpenEntry
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSLogon.OpenEntry
api_type:
- COM
ms.assetid: 612cbab7-60cb-48bb-906e-18d9135e7a86
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e9d9ca56a877c0106c76242fe97ce43321e62e08
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775919"
---
# <a name="imslogonopenentry"></a>IMSLogon::OpenEntry

  
  
**适用于**： Outlook 
  
打开文件夹或 message 对象并返回指向要进一步提供访问权限的对象的指针。 
  
```cpp
HRESULT OpenEntry(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  LPCIID lpInterface,
  ULONG ulOpenFlags,
  ULONG FAR * lpulObjType,
  LPUNKNOWN FAR * lppUnk
);
```

## <a name="parameters"></a>参数

 _cbEntryID_
  
> [in]以字节为单位_lpEntryID_参数指向的项标识符的大小。 
    
 _lpEntryID_
  
> [in]指向要打开的文件夹或邮件的对象的项标识符的地址的指针。 
    
 _lpInterface_
  
> [in]指向对象的接口标识符 (IID) 的指针。 传递 NULL 指示，该对象强制转换为标准接口此类对象。 _LpInterface_参数还可以设置为适当的接口的对象的标识符。 
    
 _ulOpenFlags_
  
> [in]位掩码的标志，控制如何打开对象。 可以设置以下标志：
    
MAPI_BEST_ACCESS 
  
> 应与为用户和最大客户端应用程序权限允许的最大权限打开对象。 例如，如果客户端具有读/写权限，则对象打开具有读/写权限;如果客户端具有只读权限，则打开对象时具有只读权限。 客户端可以通过获取**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性来检索的权限级别。
    
MAPI_DEFERRED_ERRORS 
  
> 若要成功执行，即使基础对象不是可用于呼叫的应用程序，即允许该呼叫。 如果对象不可用，对对象的后续调用可能会返回错误。
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下，对象在创建具有只读权限，并以为，读/写权限授予客户端不起作用。 
    
 _lpulObjType_
  
> [输出]一个指向打开的对象的类型。
    
 _lppUnk_
  
> [输出]指向打开的对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>说明

MAPI 调用**IMSLogon::OpenEntry**方法打开邮件存储区中的文件夹或一条消息。 要打开的对象的项标识符中传递 MAPI。 消息存储提供程序应返回使进一步访问_lppUnk_参数中指定的对象的指针。 
  
MAPI 调用**IMSLogon::OpenEntry**之前，首先确定给定的邮件或文件夹条目标识符匹配一个注册的此消息存储提供程序。 有关如何存储提供程序注册项标识符的详细信息，请参阅[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)。
  
 **IMSLogon::OpenEntry**相同的[IMsgStore::OpenEntry](imsgstore-openentry.md)方法的消息存储对象，只是客户端不会调用**IMSLogon::OpenEntry**;MAPI 调用**IMSLogon::OpenEntry**处理**IMAPISession::OpenEntry**方法时。 应使用**IMSLogon::OpenEntry**打开的对象会被视为完全相同对象打开使用消息存储对象;具体而言，发布的消息存储对象时，应无效对象使用此呼叫打开。 
  
## <a name="see-also"></a>另请参阅



[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)
  
[IMsgStore::OpenEntry](imsgstore-openentry.md)
  
[IMSLogon : IUnknown](imslogoniunknown.md)

