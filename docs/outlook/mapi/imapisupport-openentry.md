---
title: IMAPISupportOpenEntry
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.OpenEntry
api_type:
- COM
ms.assetid: 84662230-6a25-4403-b87e-871427a40c6e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: cfbb799336aa1e75fa36e03e55d82c3af3409f10
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409613"
---
# <a name="imapisupportopenentry"></a>IMAPISupport::OpenEntry

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开一个对象并返回一个接口指针以供进一步访问。 
  
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
  
> 实时条目标识符中由_lpEntryID_参数指向的字节数。 
    
 _lpEntryID_
  
> 实时指向要打开的对象的条目标识符的指针。
    
 _lpInterface_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问对象的接口。 在返回的对象的标准接口中传递 NULL 结果。 例如, 如果要打开的对象是一条消息, 则标准接口是[IMessage](imessageimapiprop.md);对于文件夹, 它是[IMAPIFolder](imapifolderimapicontainer.md)。 通讯簿对象的标准接口是[IDistList](idistlistimapicontainer.md)用于邮件用户的通讯组列表和[IMailUser](imailuserimapiprop.md) 。 
    
 _ulOpenFlags_
  
> 实时用于控制对象打开方式的标志的位掩码。 可以设置以下标志:
    
MAPI_BEST_ACCESS 
  
> 请求使用呼叫者允许的最大网络权限打开对象。 例如, 如果调用方具有读/写权限, 则应以读/写方式打开对象;如果调用方具有只读权限, 则应以只读方式打开该对象。 
    
MAPI_DEFERRED_ERRORS 
  
> 允许**OpenEntry**成功返回, 在调用方完全可以访问对象之前。 如果对象不可访问, 则进行后续的对象调用会导致错误。 
    
MAPI_MODIFY 
  
> 请求读取/写入权限。 默认情况下, 对象以只读方式打开, 并且在假定已授予读/写权限时, 调用方不应这样做。 
    
 _lpulObjType_
  
> 排除一个指针, 指向打开的对象的类型。
    
 _lppUnk_
  
> 排除指向打开的对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功打开对象。
    
MAPI_E_NO_ACCESS 
  
> 试图修改只读对象, 或试图访问用户对其没有足够权限的对象的访问权限。
    
MAPI_E_NOT_FOUND 
  
> 没有与_lpEntryID_参数中传递的条目标识符关联的对象。 
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 在_lpEntryID_参数中传递的条目标识符的格式无法识别。 如果包含该对象的通讯簿提供程序未打开, 通常会返回此值。 
    
## <a name="remarks"></a>说明

**IMAPISupport:: OpenEntry**方法是为所有服务提供程序支持对象实现的。 服务提供程序调用**IMAPISupport:: OpenEntry**以检索指向可用于访问特定对象的接口的指针。 
  
## <a name="notes-to-callers"></a>给调用方的说明

仅当您不知道要打开的对象类型时, 才会调用**IMAPISupport:: OpenEntry** 。 如果您知道要打开文件夹或邮件, 请调用[IMsgStore:: OpenEntry](imsgstore-openentry.md) 。 如果您知道要打开通讯簿容器、邮件用户或通讯组列表, 请调用[IAddrBook:: OpenEntry](iaddrbook-openentry.md)。 这些更具体的方法比**IMAPISupport:: OpenEntry**更快。 
  
 **IMAPISupport:: OpenEntry**以只读方式打开所有对象, 除非您在_ulFlags_参数中设置 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志, 并且您的权限足够。 设置其中一个标志并不能保证特定类型的访问权限;您授予的权限取决于您的访问级别、对象和拥有该对象的服务提供程序。 若要确定打开的对象的访问级别, 请检索其**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性。
  
检查_lpulObjType_参数中返回的值, 以确定返回的对象类型是您所期望的。 如果对象类型是预期的, 则将指针从_lppUnk_参数转换为适当类型的指针。 例如, 如果您打开一个文件夹, 则会将_lppUnk_转换为 LPMAPIFOLDER 类型的指针。 
  
## <a name="see-also"></a>另请参阅



[IMAPISupport : IUnknown](imapisupportiunknown.md)

