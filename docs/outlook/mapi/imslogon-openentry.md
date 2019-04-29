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
  
打开一个文件夹或邮件对象, 并返回指向该对象的指针, 以提供进一步的访问权限。 
  
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
  
> 实时由_lpEntryID_参数指向的条目标识符的大小 (以字节为单位)。 
    
 _lpEntryID_
  
> 实时一个指针, 指向要打开的文件夹或邮件对象的条目标识符的地址。 
    
 _lpInterface_
  
> 实时指向对象的接口标识符 (IID) 的指针。 传递 NULL 表示将对象强制转换为此类对象的标准接口。 也可以将_lpInterface_参数设置为对象的相应接口的标识符。 
    
 _ulOpenFlags_
  
> 实时用于控制对象打开方式的标志的位掩码。 可以设置以下标志:
    
MAPI_BEST_ACCESS 
  
> 应使用用户允许的最大权限和最大客户端应用程序权限打开该对象。 例如, 如果客户端具有读/写权限, 则该对象以读/写权限打开;如果客户端具有只读权限, 则将以只读权限打开该对象。 客户端可以通过获取**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性来检索权限级别。
    
MAPI_DEFERRED_ERRORS 
  
> 即使基础对象对调用应用程序不可用, 也允许调用成功。 如果该对象不可用, 则对该对象的后续调用可能会返回一个错误。
    
MAPI_MODIFY 
  
> 请求读取/写入权限。 默认情况下, 创建具有只读权限的对象, 并且客户端不应在假定已授予读/写权限时才起作用。 
    
 _lpulObjType_
  
> 排除一个指针, 指向打开的对象的类型。
    
 _lppUnk_
  
> 排除指向指向已打开对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>说明

MAPI 调用**IMSLogon:: OpenEntry**方法打开邮件存储中的文件夹或邮件。 MAPI 传递在要打开的对象的条目标识符中。 邮件存储区提供程序应返回一个指针, 使您能够进一步访问_lppUnk_参数中指定的对象。 
  
在 MAPI 调用**IMSLogon:: OpenEntry**之前, 首先确定给定的邮件或文件夹条目标识符与此邮件存储提供程序注册的条目标识符相匹配。 有关存储提供程序如何注册条目标识符的详细信息, 请参阅[IMAPISupport:: SetProviderUID](imapisupport-setprovideruid.md)。
  
 **IMSLogon:: OpenEntry**与邮件存储对象的[IMsgStore:: OpenEntry](imsgstore-openentry.md)方法相同, 不同之处在于客户端不会调用**IMSLogon:: OpenEntry**;MAPI 调用**IMSLogon:: OpenEntry**当它处理**IMAPISession:: OpenEntry**方法时。 使用**IMSLogon:: OpenEntry**打开的对象的处理方式应与使用邮件存储对象打开的对象完全相同;特别是, 在释放邮件存储对象时, 使用此调用打开的对象应无效。 
  
## <a name="see-also"></a>另请参阅



[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)
  
[IMsgStore::OpenEntry](imsgstore-openentry.md)
  
[IMSLogon : IUnknown](imslogoniunknown.md)

