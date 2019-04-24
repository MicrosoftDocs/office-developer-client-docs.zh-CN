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
  
打开包含驻留在主机通讯簿提供程序中的数据的收件人条目。
  
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
  
> 实时模板标识符中由_lpTemplateID_参数指向的字节数。 
    
 _lpTemplateID_
  
> 实时指向要打开的收件人条目的模板标识符或**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性的指针。
    
 _ulTemplateFlags_
  
> 实时标志的位掩码, 用于指示如何打开由模板标识符表示的条目。 可以设置以下标志:
    
FILL_ENTRY 
  
> 主机提供程序根据模板标识符所表示的条目, 在其容器中创建新条目。 **IABLogon:: OpenTemplateID**方法应使用_lpMAPIPropData_参数中的[IMAPIProp: IUnknown](imapipropiunknown.md)实现来执行主机提供程序输入的特定初始化, 或返回自定义**IMAPIProp** _lppMAPIPropNew_参数中的接口实现。 
    
 _lpMAPIPropData_
  
> 实时指向主机提供程序的 property 对象和实现的接口的指针, 该接口派生自**IMAPIProp**。
    
 _lpInterface_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示要在_lppMAPIPropNew_参数中返回的接口指针的类型。 传递**null**将返回标准消息用户界面[IMailUser: IMAPIProp](imailuserimapiprop.md)。
    
 _lppMAPIPropNew_
  
> 排除指向绑定属性对象的指针, 以及从**IMAPIProp**派生的接口的实现。
    
 _lpMAPIPropSibling_
  
> 排除保留必须为**null**。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 适当的代码已成功绑定到主机提供程序中的相关数据。
    
MAPI_E_NO_SUPPORT 
  
> 对象不支持模板 id。
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 通讯簿提供程序无法识别_lpTemplateID_参数中传递的模板标识符。 
    
## <a name="remarks"></a>注解

**IABLogon:: OpenTemplateID**方法仅由通讯簿提供程序实现, 这些提供程序需要保持对位于主机提供程序的容器中的项的副本的控制。 实现**OpenTemplateID**的提供程序称为外部通讯簿提供程序。 主机提供程序调用[IMAPISupport:: OpenTemplateID](imapisupport-opentemplateid.md)以创建复制的条目或打开复制的条目, 并在对**IABLogon:: OpenTemplateID**的调用中进行 MAPI 传递。 **IABLogon:: OpenTemplateID**打开条目并将控制它的代码绑定到主机提供程序中的数据。 
  
而不是使用条目标识符, **IABLogon:: OpenTemplateID**使用其他属性, 即条目的模板标识符 ( **PR_TEMPLATEID**)。 对于其代码必须绑定到主机提供程序中的数据的条目, 应支持模板标识符。
  
通讯簿提供商应实现 IABLogon 的一些示例 **:: OpenTemplateID**如下所示: 
  
- 定期更新复制的条目的数据, 以使其与原始条目保持同步。
    
- 若要实现宿主提供程序无法实现的功能, 例如, 从服务器上的数据动态填充显示在项的详细信息表中的列表。
    
- 控制主机提供程序的条目中的属性与原始条目之间的交互, 例如, 从包含不同的详细信息显示中的编辑控件的值计算**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))地址的组件。
    
## <a name="notes-to-implementers"></a>针对实现者的说明

当主机提供程序从提供程序中复制或创建一个条目, 并通过**IABLogon:: OpenTemplateID**提供 property 对象实现时, 您将处理大部分调用来维护该条目。 但是, 由于由主机提供程序将这些呼叫转发给您, 因此主机提供程序可以在转发呼叫之前拦截任何呼叫并执行自定义处理。
  
您应在属性对象实现中使用以下准则:
  
- 调用[IMAPIProp:: GetProps](imapiprop-getprops.md)时, 确定该请求是否针对的是计算的属性, 如果是, 则处理它。 将 noncomputed 属性的所有请求都转移到主机提供程序。 
    
- 如果调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)来打开除详细信息显示表之外的任何表, 请处理该请求。 大多数表无法精确复制到主机提供程序。 必须为这些请求的表生成**IMAPITable**实现。 必须将详细信息表**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性复制到主机提供程序。 这将允许此提供程序在本地生成表。 您可能想要包装显示表实现以生成显示表通知。 
    
- 调用[IMAPIProp:: SetProps](imapiprop-setprops.md)时, 主机提供程序可以在允许您设置属性之前验证数据。 您可以验证是否已设置或计算所有必需的属性。 如果检测到错误, 则返回相应的错误值, 如果可以, 还可以通过[IMAPIProp:: GetLastError](imapiprop-getlasterror.md)对任何其他说明进行说明。
    
- 当调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)时, 主机提供程序可能需要在保存条目之前执行处理。 应在主机提供程序的条目中保存受更改的属性 (如新地址) 影响的任何数据。 
    
通常情况下, 您对传递回主机提供程序的项的实现将截获所有方法, 以执行相关属性的特定于上下文的操作。 如果在_ulTemplateFlags_参数中传递了 FILL_ENTRY 标志, 请设置该条目的所有属性。 
  
如果您在_lppMAPIPropNew_参数中返回新的 property 对象, 请调用主机提供程序的 property 对象的[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx)方法来维护引用。 通过绑定对象在_lppMAPIPropNew_中返回的**IMAPIProp**实现的所有调用都应路由到主机 property 对象中其对应的方法, 然后由绑定的对象进行处理。 
  
通过绑定属性对象传递的任何命名属性的属性标识符都位于提供程序的标识符命名空间中。 您的[IMAPIProp:: GetNamesFromIDs](imapiprop-getnamesfromids.md)方法的实现应确定属性的名称, 以便它可以执行任何特定于模板的任务。 同样, 您的提供程序传递给主机提供程序的属性也必须在您的命名空间中。 例如, 如果在**OpenTemplateID**中设置命名的属性, 则应使用您的名称的一个标识符 (如有必要, 可通过调用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)方法来创建它)。 
  
如果您不知道在_lpTemplateID_中传递的条目标识符, 则返回 MAPI_E_UNKNOWN_ENTRYID。
  
有关如何使用通讯簿模板标识符的详细信息, 请参阅[充当外部通讯簿提供程序](acting-as-a-foreign-address-book-provider.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md)
  
[IPropData : IMAPIProp](ipropdataimapiprop.md)
  
[PidTagTemplateid 规范属性](pidtagtemplateid-canonical-property.md)
  
[IABLogon : IUnknown](iablogoniunknown.md)

