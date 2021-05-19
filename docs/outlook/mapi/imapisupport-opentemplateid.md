---
title: IMAPISupportOpenTemplateID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.OpenTemplateID
api_type:
- COM
ms.assetid: 532f7af0-b2cc-49dd-b1de-e3ec1dc9a3e7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 07aa508b473f4a87d5b4909f83771549c301a600
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418503"
---
# <a name="imapisupportopentemplateid"></a>IMAPISupport::OpenTemplateID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在外通讯簿提供程序中打开收件人条目。
  
```cpp
HRESULT OpenTemplateID(
ULONG cbTemplateID,
LPENTRYID lpTemplateID,
ULONG ulTemplateFlags,
LPMAPIPROP lpMAPIPropData,
LPCIID lpInterface,
LPMAPIPROP FAR * lppMAPIPropNew,
LPMAPIPROP lpMAPIPropSibling
);
```

## <a name="parameters"></a>参数

 _cbTemplateID_
  
> [in]  _lpTemplateID_ 指向的模板标识符中的字节计数。 
    
 _lpTemplateID_
  
> [in]指向要打开的收件人 **PR_TEMPLATEID (** [PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 模板标识符的指针。
    
 _ulTemplateFlags_
  
> [in]用于描述如何打开条目的标志的位掩码。 可以设置以下标志：
    
FILL_ENTRY 
  
> 正在创建一个新条目。 当外提供程序收到来自 MAPI 的后续 [IABLogon：：OpenTemplateID](iablogon-opentemplateid.md) 调用时，它可以通过修改  _lpMAPIPropData_ 参数指向的属性或返回  _lppMAPIPropNew_ 中的特定接口实现来控制如何设置新条目的属性来控制条目的创建方式。 
    
 _lpMAPIPropData_
  
> [in]指向调用方用于访问条目的接口实现的指针。 这是一个实现，该实现是外提供程序可以包装自己的实现，并返回到  _lppMAPIPropNew_ 参数中。 _lpMAPIPropData_ 参数必须指向从 [IMAPIProp ： IUnknown](imapipropiunknown.md)派生并支持 _在 lpInterface_ 参数中请求的接口的读/写接口实现。 
    
 _lpInterface_
  
> [in]指向接口标识符的指针 (IID) 表示用于访问条目的接口。 _lppMAPIPropNew_ 参数指向 _由 lpInterface_ 指定的类型的接口。 传递 NULL 将返回消息传递用户的标准界面，IID_IMailUser。 
    
 _lppMAPIPropNew_
  
> [out]指向外提供程序提供的用于访问条目的接口实现的指针。
    
 _lpMAPIPropSibling_
  
> 保留;必须为 NULL。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 绑定过程成功。
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 不存在外通讯簿提供程序。
    
## <a name="remarks"></a>备注

**IMAPISupport：：OpenTemplateID** 方法仅为通讯簿提供程序支持对象实现。 **OpenTemplateID** 仅由通讯簿提供程序调用，这些通讯簿提供程序可以充当属于其他通讯簿提供程序（也称为"外提供程序）"的条目的主机。 主机提供程序调用 **OpenTemplateID** 以打开一个外项，当主机提供程序中的数据绑定到该外提供程序中的代码时，将发生此情况。 
  
## <a name="notes-to-callers"></a>给调用方的说明

仅在支持存储具有来自外通讯簿提供程序的模板标识符的条目时，才调用 **OpenTemplateID。** 此类支持对 [IABContainer：：CreateEntry](iabcontainer-createentry.md) 和 [IABLogon：：OpenEntry](iablogon-openentry.md) 实现提出了其他要求。 有关详细信息，请参阅这些方法的说明和充当主机 [通讯簿提供程序](acting-as-a-host-address-book-provider.md)。
  
如果 **OpenTemplateID** 调用作为绑定接口返回传入的相同属性对象实现，可以释放对属性对象的引用。 这是因为外部提供程序已调用对象的 **AddRef** 方法来保留其自己的引用。 如果外提供程序不需要保留对属性对象的引用， **则 OpenTemplateID** 将返回未绑定的属性对象。 
  
如果 **OpenTemplateID** 失败MAPI_E_UNKNOWN_ENTRYID，请尝试继续操作，将条目视为只读。 
  
## <a name="see-also"></a>另请参阅



[IABLogon::OpenTemplateID](iablogon-opentemplateid.md)
  
[IPropData : IMAPIProp](ipropdataimapiprop.md)
  
[PidTagTemplateid 规范属性](pidtagtemplateid-canonical-property.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

