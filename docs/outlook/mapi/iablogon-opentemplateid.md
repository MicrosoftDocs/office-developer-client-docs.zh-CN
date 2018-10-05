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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: bc68878a25873533162df7e1671e483c3bb77865
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25384631"
---
# <a name="iablogonopentemplateid"></a>IABLogon::OpenTemplateID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开具有数据驻留在承载通讯簿提供程序中的收件人条目。
  
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
  
> [in]在模板标识符_lpTemplateID_参数指向字节数。 
    
 _lpTemplateID_
  
> [in]一个指向模板标识符或**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性，要打开的收件人条目。
    
 _ulTemplateFlags_
  
> [in]用于指示如何打开由模板标识符的条目的标志位掩码。 可以设置以下标记：
    
FILL_ENTRY 
  
> 宿主提供程序在基于由模板标识符项其容器中创建一个新的条目。 **IABLogon::OpenTemplateID**方法也应使用执行特定初始化宿主提供程序的条目的[IMAPIProp: IUnknown](imapipropiunknown.md) _lpMAPIPropData_参数或返回一个自定义**IMAPIProp 中的实现**接口_lppMAPIPropNew_参数中的实现。 
    
 _lpMAPIPropData_
  
> [in]指向主机提供商的 property 对象和接口实现派生自**IMAPIProp**。
    
 _lpInterface_
  
> [in]一个指向代表类型的接口指针_lppMAPIPropNew_参数中要返回的接口标识符 (IID)。 传递**null**返回消息用户界面的标准[IMailUser: IMAPIProp](imailuserimapiprop.md)。
    
 _lppMAPIPropNew_
  
> [输出]一个指向绑定的 property 对象和接口派生自**IMAPIProp**的实现。
    
 _lpMAPIPropSibling_
  
> [输出]保留;必须为**空**。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 相应的代码已成功绑定到宿主提供程序中的相关数据。
    
MAPI_E_NO_SUPPORT 
  
> 对象不支持模板 Id。
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 通过通讯簿提供程序无法识别_lpTemplateID_参数中传递的模板标识符。 
    
## <a name="remarks"></a>说明

仅由需要维护控制它们位于的宿主提供商的容器中的项的副本的通讯簿提供程序实现**IABLogon::OpenTemplateID**方法。 提供程序实现**OpenTemplateID**称为外的通讯簿提供程序。 宿主提供程序调用[IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md)创建复制的条目或打开复制的条目，并在调用**IABLogon::OpenTemplateID**传递 MAPI。 **IABLogon::OpenTemplateID**将打开条目，并将绑定控件到宿主提供程序中的数据的代码。 
  
而不是使用的项标识符， **IABLogon::OpenTemplateID**使用另一个属性，该条目模板标识符， **PR_TEMPLATEID**。 模板标识符应支持其代码必须绑定到宿主提供程序中的数据的条目。
  
某些的通讯簿提供程序应在何时实现**IABLogon::OpenTemplateID**示例如下所示： 
  
- 定期更新复制项的数据，使其保持同步与原始。
    
- 若要实现宿主提供程序无法实现，如动态填充列表项的详细信息表中显示从服务器上的数据的功能。
    
- 若要控制宿主提供程序的条目中的属性和原始条目中，如计算**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 从包含不同的编辑控件中显示的详细信息的值之间的交互地址的组件。
    
## <a name="notes-to-implementers"></a>针对实现者的说明

当宿主提供程序复制或从您的提供商创建一个条目，并提供通过**IABLogon::OpenTemplateID**属性对象实现时，您处理大部分呼叫维护条目。 但是，因为它是主机提供这些将呼叫转接到您，宿主提供程序可以截获任何呼叫，并执行自定义处理，然后转接呼叫。
  
您属性对象实现中，您应使用以下准则：
  
- 调用[IMAPIProp::GetProps](imapiprop-getprops.md)时，确定是否此请求所使用的计算属性，如果是，处理它。 将为未计算属性的所有请求都传送到宿主提供程序。 
    
- 当[IMAPIProp::OpenProperty](imapiprop-openproperty.md)调用它以打开任何表格中的除详细信息显示表，处理请求。 大多数表无法准确地复制到宿主提供程序。 您必须生成这些请求表的**IMAPITable**实现。 详细信息表**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性必须将复制到宿主提供程序。 这样，此提供程序可以生成本地表。 您可能希望换行显示表实现，以生成显示表通知。 
    
- 当调用[IMAPIProp::SetProps](imapiprop-setprops.md)时，宿主提供程序可以让您设置属性之前验证的数据。 您可以验证所有必要的属性已设置或计算。 如果检测到错误时，返回相应的错误值，如果可能，通过[IMAPIProp::GetLastError](imapiprop-getlasterror.md)任何其他说明。
    
- 当调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)时，宿主提供程序可能需要执行处理之前保存该条目。 您应该保存受已更改的属性，如宿主提供程序的条目中的新地址的任何数据。 
    
一般情况下，返回对宿主提供程序进行传递的条目的实现 intercept 的所有方法执行的相关属性的上下文特定操作。 如果_ulTemplateFlags_参数中传递 FILL_ENTRY 标志，则设置该条目的所有属性。 
  
如果_lppMAPIPropNew_参数中返回新的 property 对象，请调用要维护的引用的宿主提供程序的属性对象的[IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx)方法。 通过**IMAPIProp**实现_lppMAPIPropNew_中返回的绑定对象的所有呼叫将都路由到其对应的方法中的主机属性对象处理绑定对象后。 
  
通过绑定的属性对象传递任何命名属性的属性的标识符是提供程序的标识符命名空间中。 [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)方法的实现应确定属性的名称，以便它可以执行任何特定于模板的任务。 同样，您的提供商将传递给宿主提供程序的属性也必须在您的命名空间。 例如，如果**OpenTemplateID**中设置的命名的属性，您应使用您标识符之一的名称 — 通过调用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)方法有必要，创建它。 
  
如果您不认识_lpTemplateID_中传递的项标识符，返回 MAPI_E_UNKNOWN_ENTRYID。
  
有关如何使用地址簿模板标识符的详细信息，请参阅[充当外的通讯簿提供程序](acting-as-a-foreign-address-book-provider.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md)
  
[IPropData : IMAPIProp](ipropdataimapiprop.md)
  
[PidTagTemplateid 规范属性](pidtagtemplateid-canonical-property.md)
  
[IABLogon : IUnknown](iablogoniunknown.md)

