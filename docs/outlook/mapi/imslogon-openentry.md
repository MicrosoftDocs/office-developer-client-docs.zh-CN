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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 544aaaace18a9d26972e6484803b63a1ee7060fc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416298"
---
# <a name="imslogonopenentry"></a>IMSLogon::OpenEntry

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开文件夹或邮件对象，并返回指向该对象的指针以提供进一步的访问。 
  
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
  
> [in]  _lpEntryID_ 参数指向的条目标识符的大小（以字节为单位）。 
    
 _lpEntryID_
  
> [in]指向要打开的文件夹或邮件对象的条目标识符的地址的指针。 
    
 _lpInterface_
  
> [in]指向对象的 IID (接口) 指针。 传递 NULL 表示对象被强制转换到此类对象的标准接口。 _还可以将 lpInterface_ 参数设置为对象相应接口的标识符。 
    
 _ulOpenFlags_
  
> [in]控制对象打开方式的标志的位掩码。 可以设置以下标志：
    
MAPI_BEST_ACCESS 
  
> 该对象应该使用用户允许的最大权限和最大客户端应用程序权限打开。 例如，如果客户端具有读/写权限，则使用读/写权限打开对象;如果客户端具有只读权限，则使用只读权限打开对象。 客户端可以通过获取[PidTagAccessLevel](pidtagaccesslevel-canonical-property.md) PR_ACCESS_LEVEL (权限) 级别。 
    
MAPI_DEFERRED_ERRORS 
  
> 即使基础对象对调用应用程序不可用，也允许调用成功。 如果该对象不可用，则对该对象的后续调用可能会返回错误。
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下，使用只读权限创建对象，客户端不应在已授予读/写权限的假设下工作。 
    
 _lpulObjType_
  
> [out]指向已打开对象的类型的指针。
    
 _lppUnk_
  
> [out]指向已打开对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

MAPI 调用 **IMSLogon：：OpenEntry** 方法打开邮件存储中的文件夹或邮件。 MAPI 将传递要打开的对象的条目标识符。 邮件存储提供程序应返回一个指针，允许进一步访问  _lppUnk_ 参数中指定的对象。 
  
在 MAPI 调用 **IMSLogon：：OpenEntry** 之前，它首先确定给定的邮件或文件夹条目标识符与由此消息存储提供程序注册的邮件或文件夹条目标识符匹配。 有关存储提供程序如何注册条目标识符的信息，请参阅 [IMAPISupport：：SetProviderUID](imapisupport-setprovideruid.md)。
  
 **IMSLogon：：OpenEntry** 与消息存储对象的 [IMsgStore：：OpenEntry](imsgstore-openentry.md)方法相同，只不过客户端不调用 **IMSLogon：：OpenEntry**;MAPI 在处理 **IMAPISession：：OpenEntry 方法时调用 IMSLogon：：OpenEntry。**  使用 **IMSLogon：：OpenEntry** 打开的对象处理方式应该与使用消息存储对象打开的对象完全相同;特别是，当释放邮件存储对象时，使用此调用打开的对象应失效。 
  
## <a name="see-also"></a>另请参阅



[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)
  
[IMsgStore::OpenEntry](imsgstore-openentry.md)
  
[IMSLogon : IUnknown](imslogoniunknown.md)

