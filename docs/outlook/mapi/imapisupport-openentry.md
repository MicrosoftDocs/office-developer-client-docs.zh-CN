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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 04bf7f2ddda7377df72417df2472246a2cf329bf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775649"
---
# <a name="imapisupportopenentry"></a>IMAPISupport::OpenEntry

  
  
**适用于**： Outlook 
  
打开一个对象并返回进一步访问的接口指针。 
  
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
  
> [in]在_lpEntryID_参数指向的项标识符的字节数。 
    
 _lpEntryID_
  
> [in]指向要打开的对象的项标识符的指针。
    
 _lpInterface_
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问该对象的接口的指针。 传递空结果中要返回的对象的标准接口。 例如，如果要在打开的对象是一条消息，标准接口是[IMessage](imessageimapiprop.md);对于文件夹，则[IMAPIFolder](imapifolderimapicontainer.md)。 地址簿对象的标准接口是[IDistList](idistlistimapicontainer.md)通讯组列表和[IMailUser](imailuserimapiprop.md)消息用户。 
    
 _ulOpenFlags_
  
> [in]位掩码的标志，控制如何打开对象。 可以设置以下标志：
    
MAPI_BEST_ACCESS 
  
> 请求，与呼叫者允许的最大网络权限打开对象。 例如，如果呼叫者具有读/写权限，该对象应打开以读/写;如果呼叫者具有只读权限，则应以只读方式打开对象。 
    
MAPI_DEFERRED_ERRORS 
  
> 允许**OpenEntry**返回成功，原因可能是完全可与呼叫者访问对象之前。 如果对象不是可访问的则进行后续对象呼叫会导致出错。 
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下，以只读方式打开对象和呼叫者以为，读/写权限授予不起作用。 
    
 _lpulObjType_
  
> [输出]一个指向打开的对象的类型。
    
 _lppUnk_
  
> [输出]指向打开的对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功打开对象。
    
MAPI_E_NO_ACCESS 
  
> 尝试修改只读对象，或尝试访问其用户没有足够的权限的对象。
    
MAPI_E_NOT_FOUND 
  
> 没有与_lpEntryID_参数中传递的项标识符关联的对象。 
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 无法识别格式_lpEntryID_参数中传递的项标识符。 如果包含对象的通讯簿提供程序未打开，则通常会返回此值。 
    
## <a name="remarks"></a>说明

**IMAPISupport::OpenEntry**方法将执行所有服务提供商支持对象。 服务提供商调用**IMAPISupport::OpenEntry**检索可用于访问特定对象的接口的指针。 
  
## <a name="notes-to-callers"></a>给调用方的说明

仅当您不知道您打开哪种类型的对象时，请调用**IMAPISupport::OpenEntry** 。 如果您知道要打开文件夹或一条消息，请改为呼叫[IMsgStore::OpenEntry](imsgstore-openentry.md) 。 如果您知道要打开通讯簿容器、 邮件用户或通讯组列表，请调用[IAddrBook::OpenEntry](iaddrbook-openentry.md)。 这些更加具体方法是比**IMAPISupport::OpenEntry**速度更快。 
  
 **IMAPISupport::OpenEntry**打开所有对象为只读，除非_ulFlags_参数中设置 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志并且您的权限不足。 这些标志之一设置不保证特定类型的访问;您已被授予的权限取决于您的访问级别、 对象和拥有该对象的服务提供程序。 若要确定打开的对象的访问级别，检索其**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性。
  
检查以确定返回的对象类型是您的预期_lpulObjType_参数中返回的值。 如果对象类型是预期，强制转换为适当类型的指针的指针从_lppUnk_参数。 例如，如果您打开一个文件夹，强制转换为的类型 LPMAPIFOLDER 指针_lppUnk_ 。 
  
## <a name="see-also"></a>另请参阅



[IMAPISupport : IUnknown](imapisupportiunknown.md)

