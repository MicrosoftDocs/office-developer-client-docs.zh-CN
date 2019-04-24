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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326360"
---
# <a name="imapisupportopentemplateid"></a>IMAPISupport::OpenTemplateID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开外部通讯簿提供程序中的收件人条目。
  
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
  
> 实时模板标识符中由_lpTemplateID_指向的字节数。 
    
 _lpTemplateID_
  
> 实时指向要打开的收件人条目的模板标识符**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性的指针。
    
 _ulTemplateFlags_
  
> 实时用于描述如何打开条目的标志位掩码。 可以设置以下标志:
    
FILL_ENTRY 
  
> 正在创建新条目。 当外部提供程序接收到来自 MAPI 的后续[IABLogon:: OpenTemplateID](iablogon-opentemplateid.md)呼叫时, 它可以通过修改由_lpMAPIPropData_参数指向的属性或返回特定接口来控制创建条目的方式。_lppMAPIPropNew_中的实现来控制如何设置新条目的属性。 
    
 _lpMAPIPropData_
  
> 实时指向调用方用来访问条目的接口实现的指针。 这是外部提供程序可以使用其自己的实现进行包装并在_lppMAPIPropNew_参数中返回的实现。 _lpMAPIPropData_参数必须指向从[IMAPIProp: IUnknown](imapipropiunknown.md)派生并支持在_lpInterface_参数中请求的接口的读/写接口实现。 
    
 _lpInterface_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问该条目的接口。 _lppMAPIPropNew_参数指向_lpInterface_指定的类型的接口。 传递 NULL 将返回邮件用户的标准接口 IID_IMailUser。 
    
 _lppMAPIPropNew_
  
> 排除指向外部提供程序用于访问条目的接口实现的指针。
    
 _lpMAPIPropSibling_
  
> 保留必须为 NULL。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 绑定过程已成功。
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 外部通讯簿提供程序不存在。
    
## <a name="remarks"></a>注解

仅对通讯簿提供程序支持对象实现**IMAPISupport:: OpenTemplateID**方法。 **OpenTemplateID**只能由通讯簿提供程序调用, 该提供程序可充当属于其他通讯簿提供程序 (也称为外部提供程序) 的条目的主机。 主机提供程序调用**OpenTemplateID**以打开外接程序, 当主机提供程序中的数据绑定到外部提供程序中的代码时, 将发生这种情况。 
  
## <a name="notes-to-callers"></a>给调用方的说明

仅当您支持通过外部通讯簿提供程序存储具有模板标识符的条目时, 才会调用**OpenTemplateID** 。 此类支持对[IABContainer:: CreateEntry](iabcontainer-createentry.md)和[IABLogon:: OpenEntry](iablogon-openentry.md)实现施加了其他要求。 有关详细信息, 请参阅这些方法的说明和[充当主机通讯簿提供程序](acting-as-a-host-address-book-provider.md)。
  
如果**OpenTemplateID**调用作为绑定接口返回, 则表示您传递的属性对象实现相同, 您可以释放对属性对象的引用。 这是因为外部提供程序已调用对象的**AddRef**方法来保留自己的引用。 如果外部提供程序不需要保留对 property 对象的引用, 则**OpenTemplateID**将返回未绑定的属性对象。 
  
如果**OpenTemplateID**在 MAPI_E_UNKNOWN_ENTRYID 中失败, 请尝试通过将该条目视为只读来继续。 
  
## <a name="see-also"></a>另请参阅



[IABLogon::OpenTemplateID](iablogon-opentemplateid.md)
  
[IPropData : IMAPIProp](ipropdataimapiprop.md)
  
[PidTagTemplateid 规范属性](pidtagtemplateid-canonical-property.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

