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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f99843bcdf3689acad72145a33d6a9804175a413
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775654"
---
# <a name="imapisupportopentemplateid"></a>IMAPISupport::OpenTemplateID

  
  
**适用于**： Outlook 
  
在外部地址簿提供程序中打开一个收件人的项。
  
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
  
> [in]由_lpTemplateID_指向该模板标识符中字节数。 
    
 _lpTemplateID_
  
> [in]一个指向模板标识符的收件人的条目，打开**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性。
    
 _ulTemplateFlags_
  
> [in]用于介绍如何打开条目的标志位掩码。 可以设置以下标记：
    
FILL_ENTRY 
  
> 正在创建一个新的条目。 外的提供程序接收 MAPI 后续[IABLogon::OpenTemplateID](iablogon-opentemplateid.md)调用，它可以控制如何通过修改属性指向通过_lpMAPIPropData_参数或返回特定的接口创建条目_lppMAPIPropNew_来控制如何设置新项的属性中的实现。 
    
 _lpMAPIPropData_
  
> [in]指向该接口实现用于访问该条目呼叫者的指针。 这是外的提供程序可以使用它自己的实现包装并_lppMAPIPropNew_参数中返回的实现。 _LpMAPIPropData_参数必须指向派生的读/写接口实现[IMAPIProp: IUnknown](imapipropiunknown.md)和支持正在请求_lpInterface_参数中的接口。 
    
 _lpInterface_
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问该条目的接口的指针。 _LppMAPIPropNew_参数指向_lpInterface_指定类型的接口。 传递 NULL 返回的消息的用户，IID_IMailUser 标准的接口。 
    
 _lppMAPIPropNew_
  
> [输出]一个指向外的提供程序提供用于访问该条目该接口实现。
    
 _lpMAPIPropSibling_
  
> 保留;必须为 NULL。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 绑定过程成功。
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 外部地址簿提供程序不存在。
    
## <a name="remarks"></a>说明

只为通讯簿提供程序支持对象实现**IMAPISupport::OpenTemplateID**方法。 仅可用作条目属于其他通讯簿提供程序，也称为外的提供程序承载的通讯簿提供程序调用**OpenTemplateID** 。 宿主提供程序调用**OpenTemplateID**打开一个外部项，宿主提供程序中的数据绑定到外的提供程序中的代码时，发生此事件。 
  
## <a name="notes-to-callers"></a>给调用方的说明

调用**OpenTemplateID** ，才支持与外部地址簿提供程序的模板标识符的条目存储。 此类支持将放在[IABContainer::CreateEntry](iabcontainer-createentry.md)和[IABLogon::OpenEntry](iablogon-openentry.md)实现的其他要求。 有关详细信息，请参阅这些方法和[充当主机通讯簿提供程序](acting-as-a-host-address-book-provider.md)的说明。
  
如果**OpenTemplateID**调用与绑定接口返回相同的属性对象实现中传递，您可以释放您对 property 对象的引用。 这是因为外的提供程序具有调用该对象的**AddRef**方法保留其自己的引用。 如果外的提供程序并不需要保存对 property object 的引用， **OpenTemplateID**将返回绑定的 property 对象。 
  
如果操作失败， **OpenTemplateID** MAPI_E_UNKNOWN_ENTRYID，尝试继续通过将视为只读的条目。 
  
## <a name="see-also"></a>另请参阅



[IABLogon::OpenTemplateID](iablogon-opentemplateid.md)
  
[IPropData : IMAPIProp](ipropdataimapiprop.md)
  
[PidTagTemplateid 规范属性](pidtagtemplateid-canonical-property.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

