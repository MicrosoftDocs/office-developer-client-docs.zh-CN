---
title: IABLogonOpenTemplateID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon.OpenTemplateID
api_type:
- COM
ms.assetid: 751c36d3-c39e-4357-a60a-88685a378de0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bc68878a25873533162df7e1671e483c3bb77865
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334746"
---
# <a name="iablogonopentemplateid"></a>IABLogon::OpenTemplateID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开具有驻留在主机通讯簿提供程序中的数据的收件人条目。
  
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
  
> [in]  _lpTemplateID_ 参数指向的模板标识符中的字节计数。 
    
 _lpTemplateID_
  
> [in]指向要打开的收件人条目的模板标识符PR_TEMPLATEID ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性的指针。
    
 _ulTemplateFlags_
  
> [in]用于指示如何打开模板标识符表示的条目的标志的位掩码。 可以设置以下标志：
    
FILL_ENTRY 
  
> 宿主提供程序正在基于模板标识符表示的条目在其容器中创建新条目。 **IABLogon：：OpenTemplateID** 方法应该使用 _lpMAPIPropData_ 参数中的 [IMAPIProp ： IUnknown](imapipropiunknown.md)实现执行主机提供程序条目的特定初始化，或在 _lppMAPIPropNew_ 参数中返回自定义 **IMAPIProp** 接口实现。 
    
 _lpMAPIPropData_
  
> [in]指向主机提供程序的属性对象以及派生自 **IMAPIProp** 的接口的实现的指针。
    
 _lpInterface_
  
> [in]指向接口标识符的指针 (IID) 表示在  _lppMAPIPropNew_ 参数中返回的接口指针的类型。 传递 **null** 将返回标准消息用户界面 [IMailUser ： IMAPIProp](imailuserimapiprop.md)。
    
 _lppMAPIPropNew_
  
> [out]指向绑定属性对象的指针和派生自 **IMAPIProp 的接口的实现**。
    
 _lpMAPIPropSibling_
  
> [out]保留;必须为 **null**。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功将相应的代码绑定到宿主提供程序中的相关数据。
    
MAPI_E_NO_SUPPORT 
  
> 对象不支持模板 ID。
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 通讯簿提供程序无法识别在  _lpTemplateID_ 参数中传递的模板标识符。 
    
## <a name="remarks"></a>备注

**IABLogon：：OpenTemplateID** 方法仅由需要维护对位于宿主提供程序容器中的条目副本的控制的通讯簿提供程序实现。 实现 **OpenTemplateID** 的提供程序称为"外通讯簿提供程序"。 主机提供商调用 [IMAPISupport：：OpenTemplateID](imapisupport-opentemplateid.md) 来创建复制的条目或打开复制的条目，MAPI 将传递对 **IABLogon：：OpenTemplateID** 的调用。 **IABLogon：：OpenTemplateID** 打开条目，将控制它的代码绑定到主机提供程序中的数据。 
  
**IABLogon：：OpenTemplateID** 不使用条目标识符，而是使用另一个属性，即条目的模板 **标识符** PR_TEMPLATEID。 对于其代码必须绑定到主机提供程序中数据的条目，应支持模板标识符。
  
通讯簿提供程序何时应实现 **IABLogon：：OpenTemplateID** 的一些示例如下所示： 
  
- 定期更新复制项的数据，以便与原始项保持同步。
    
- 实现宿主提供程序无法实现的功能，例如从服务器上数据动态填充出现在条目详细信息表中的列表。
    
- 控制主机提供程序条目中的属性与原始条目之间的交互，例如根据包含地址不同组件的编辑控件的值计算 **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 。
    
## <a name="notes-to-implementers"></a>针对实现者的说明

当主机提供程序从提供程序复制或创建条目，并且您通过 **IABLogon：：OpenTemplateID** 提供属性对象实现时，您需要处理大部分调用来维护条目。 但是，由于由主机提供商将这些呼叫转发给你，因此主机提供商可以在转发呼叫之前截获任何呼叫并执行自定义处理。
  
应该在属性对象实现中使用以下准则：
  
- 调用 [IMAPIProp：：GetProps](imapiprop-getprops.md) 时，确定请求是否针对的是计算属性，如果是，则处理它。 将未计算属性的所有请求都转移到宿主提供程序。 
    
- 调用 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 以打开除详细信息显示表之外的任何表时，请处理请求。 大多数表无法准确复制到宿主提供程序。 您必须为这些 **请求的表生成 IMAPITable** 实现。 必须将[PidTagDetailsTable](pidtagdetailstable-canonical-property.md) PR_DETAILS_TABLE (的详细信息表) 复制到主机提供程序。  这允许此提供程序在本地生成表。 您可能需要包装显示表实现以生成显示表通知。 
    
- 调用 [IMAPIProp：：SetProps](imapiprop-setprops.md) 时，主机提供程序可以先验证数据，然后再设置属性。 可以验证是否设置了或计算所有必需属性。 如果检测到错误，请返回相应的错误值，如果可以，则通过 [IMAPIProp：：GetLastError 返回任何其他说明](imapiprop-getlasterror.md)。
    
- 调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 时，宿主提供商可能需要在保存条目之前执行处理。 您应将受更改的属性（如新地址）影响的任何数据保存在宿主提供程序的条目中。 
    
通常，使传递回宿主提供程序的条目的实现截获所有方法来执行相关属性的特定于上下文的操作。 如果在  _ulTemplateFlags_ 参数中传递 FILL_ENTRY 标志，则设置条目的所有属性。 
  
如果在  _lppMAPIPropNew_ 参数中返回新的属性对象，请调用宿主提供程序的属性对象的 [IUnknown：：AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx) 方法来维护引用。 通过 _绑定对象（lppMAPIPropNew_ 中返回 **的 IMAPIProp** 实现）的所有调用应在绑定对象处理后路由到主机属性对象中的相应方法。 
  
通过绑定属性对象传递的任何命名属性的属性标识符都在你的提供程序的标识符命名空间中。 [IMAPIProp：：GetNamesFromIDs](imapiprop-getnamesfromids.md)方法的实现应确定属性的名称，以便它可以执行任何特定于模板的任务。 同样，提供程序传递给主机提供程序的属性也必须位于命名空间中。 例如，如果在 **OpenTemplateID** 中设置了命名属性，应该使用其中一个标识符作为名称，如有必要，通过调用 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 方法创建它。 
  
如果您无法识别在  _lpTemplateID_ 中传递的条目标识符，则返回MAPI_E_UNKNOWN_ENTRYID。
  
有关如何使用通讯簿模板标识符的信息，请参阅代理 [外通讯簿提供程序](acting-as-a-foreign-address-book-provider.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md)
  
[IPropData : IMAPIProp](ipropdataimapiprop.md)
  
[PidTagTemplateid 规范属性](pidtagtemplateid-canonical-property.md)
  
[IABLogon : IUnknown](iablogoniunknown.md)

