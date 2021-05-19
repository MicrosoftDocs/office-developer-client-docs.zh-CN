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
  
打开对象并返回接口指针以进一步访问。 
  
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
  
> [in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。 
    
 _lpEntryID_
  
> [in]指向要打开的对象的条目标识符的指针。
    
 _lpInterface_
  
> [in]指向接口标识符的指针 (IID) 表示用于访问对象的接口。 传递 NULL 会导致返回对象的标准接口。 例如，如果要打开的对象是一条消息，则标准接口为 [IMessage](imessageimapiprop.md);对于文件夹，它是 [IMAPIFolder](imapifolderimapicontainer.md)。 通讯簿对象的标准接口是通讯组列表的[IDistList](idistlistimapicontainer.md)和邮件用户的[IMailUser。](imailuserimapiprop.md) 
    
 _ulOpenFlags_
  
> [in]控制对象打开方式的标志的位掩码。 可以设置以下标志：
    
MAPI_BEST_ACCESS 
  
> 请求使用呼叫者允许的最大网络权限打开对象。 例如，如果调用方具有读/写权限，则对象应作为读/写打开;如果调用方具有只读权限，则对象应该以只读状态打开。 
    
MAPI_DEFERRED_ERRORS 
  
> 允许 **OpenEntry** 在调用方完全可访问该对象之前成功返回。 如果对象不可访问，则进行后续对象调用可能会导致错误。 
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下，对象以只读模式打开，并且调用方不应在已授予读/写权限的假设下工作。 
    
 _lpulObjType_
  
> [out]指向已打开对象的类型的指针。
    
 _lppUnk_
  
> [out]指向已打开对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功打开对象。
    
MAPI_E_NO_ACCESS 
  
> 试图修改只读对象，或试图访问用户权限不足的对象。
    
MAPI_E_NOT_FOUND 
  
> 没有与在  _lpEntryID_ 参数中传递的条目标识符关联的对象。 
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 在  _lpEntryID_ 参数中传递的条目标识符采用不可识别的格式。 如果包含该对象的通讯簿提供程序未打开，则通常返回此值。 
    
## <a name="remarks"></a>备注

**IMAPISupport：：OpenEntry** 方法针对所有服务提供商支持对象实现。 服务提供商调用 **IMAPISupport：：OpenEntry** 以检索指向可用于访问特定对象的接口的指针。 
  
## <a name="notes-to-callers"></a>给调用方的说明

仅在不知道要打开哪种类型的对象时调用 **IMAPISupport：：OpenEntry。** 如果您知道要打开文件夹或邮件，请改为调用[IMsgStore：：OpenEntry。](imsgstore-openentry.md) 如果您知道要打开通讯簿容器、邮件传递用户或通讯组列表，请调用 [IAddrBook：：OpenEntry](iaddrbook-openentry.md)。 这些更具体的方法比 **IMAPISupport：：OpenEntry 要快**。 
  
 **IMAPISupport：：OpenEntry** 以只读状态打开所有对象，除非您在  _ulFlags_ 参数中设置了 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志，并且您的权限已足够。 设置其中一个标志并不能保证特殊类型的访问;您授予的权限取决于您的访问级别、对象以及拥有该对象的服务提供商。 若要确定打开的对象的访问级别，请检索该对象PR_ACCESS_LEVEL ( [PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性。
  
检查  _lpulObjType_ 参数中返回的值，以确定对象类型返回的值是否与预期值一样。 如果对象类型，将指针从  _lppUnk_ 参数强制转换到相应类型的指针。 例如，如果要打开文件夹，将  _lppUnk_ 强制转换到类型 LPMAPIFOLDER 的指针。 
  
## <a name="see-also"></a>另请参阅



[IMAPISupport : IUnknown](imapisupportiunknown.md)

