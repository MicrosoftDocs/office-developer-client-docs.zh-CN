---
title: IABContainerCreateEntry
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABContainer.CreateEntry
api_type:
- COM
ms.assetid: ea1daf74-d9e3-4304-bf5d-889afeea6ae9
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9f80130279e3437dd9be947de97d3f0d4181165e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411272"
---
# <a name="iabcontainercreateentry"></a>IABContainer::CreateEntry

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
创建一个新条目，该条目可以是邮件用户、通讯组列表或其他容器。
  
```cpp
HRESULT CreateEntry(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulCreateFlags,
  LPMAPIPROP FAR * lppMAPIPropEntry
);
```

## <a name="parameters"></a>参数

 _cbEntryID_
  
> [in]  _lpEntryID_ 参数指向的条目标识符中的字节数。 
    
 _lpEntryID_
  
> [in]指向模板的条目标识符的指针，用于创建特定类型的新条目。 
    
 _ulCreateFlags_
  
> [in]控制条目创建如何执行的标志的位掩码。 可以设置以下标志：
    
CREATE_CHECK_DUP_LOOSE 
  
> 应执行松散级别的重复项检查。 松散重复项检查的实现特定于提供程序。 例如，提供程序可以将松散匹配定义为任何两个具有相同的匹配显示名称。
    
CREATE_CHECK_DUP_STRICT 
  
> 应执行严格的重复项检查级别。 严格重复项检查的实现特定于提供程序。 例如，提供程序可以将严格匹配定义为任何两个条目，这些条目具有相同的显示名称地址。
    
CREATE_REPLACE 
  
> 如果确定两者是重复项，则新条目应替换现有的条目。
    
 _lppMAPIPropEntry_
  
> [out]指向指向新创建的条目的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功创建新条目。
    
## <a name="remarks"></a>备注

**IABContainer：：CreateEntry** 方法在指定的容器中创建一个特定类型的新条目，并返回指向接口实现以进一步访问该条目的指针。 新条目是使用从容器的可用模板列表中选择的模板创建的，该模板已发布到其一对一表中。 调用方通过调用容器的[IMAPIProp：：OpenProperty](imapiprop-openproperty.md)方法并请求 PR_CREATE_TEMPLATES ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 访问容器的一) 表。  
  
## <a name="notes-to-implementers"></a>针对实现者的说明

支持 **IABContainer：：CreateEntry** 方法的所有容器都必须可修改。 使用[PidTagContainerFlags AB_MODIFIABLE PidTagContainerFlags](pidtagcontainerflags-canonical-property.md) PR_CONTAINER_FLAGS (设置容器的) 标志，以指示它是可修改的。  
  
您应支持所有  _ulCreateFlags_ 标志。 但是，这些标志的解释和使用特定于实现，也就是说，你可以确定 CREATE_CHECK_DUP_LOOSE 和 CREATE_CHECK_DUP_STRICT在实现上下文中的含义。 如果无法确定条目是否是重复项，请始终允许创建条目。 
  
某些提供程序通过匹配条目中的显示名称、邮件地址和搜索键来实现严格的条目检查;其他提供程序将匹配限制为显示名称地址。 松散条目检查通常仅通过检查显示名称实现。 
  
## <a name="notes-to-host-address-book-provider-implementers"></a>主机通讯簿提供程序实施者注意事项

如果您的容器可以从其他提供程序的模板创建条目，则 **CreateEntry** 的实现应为与所创建的条目关联的某些或所有属性提供存储。 例如，如果为条目的 **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性提供存储，则无需依赖外提供程序即可生成其详细信息对话框。 
  
如果容器可以创建支持 [PidTagTemplateid PR_TEMPLATEID (PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 项，则 **CreateEntry** 的实现必须执行以下操作：  
  
1. 调用 [IMAPISupport：：OpenTemplateID](imapisupport-opentemplateid.md) 方法。 **OpenTemplateID** 允许外提供程序的条目代码绑定到正在创建的新条目。 Foreign providers support this binding process to maintain control over entries created from their templates into the containers of host address book providers. 
    
2. 执行任何必要的初始化，并使用来自来自 **OpenTemplateID** 的 _lppMAPIPropNew 参数中的对象在 lppMAPIPropNew_ 参数中返回的项的所有属性填充新对象。
    
如果 **OpenTemplateID** 成功，将属性复制到  _lppMAPIPropNew_ 参数指向的实现，而不是直接复制到  _lpMAPIPropData_ 参数指向的实现。 像初始化来自外提供程序的其他任何条目一样，初始化新条目以脱机使用。 
  
如果 **OpenTemplateID** 返回错误 **，CreateEntry** 应该会失败。 不允许创建条目。 由于该外提供程序可以做出有关提供程序中数据的假设，因此不要创建一个模板标识符尚未成功绑定到该提供程序的条目。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当 **CreateEntry** 返回时，您可以或不能立即访问新条目的条目标识符。 在调用新条目的 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法之前，某些通讯簿提供程序才可用。 
  
尽管重复检查标志作为参数传递给 **CreateEntry，** 但重复检查操作在 **调用 SaveChanges 之前** 不会发生。 因此，诸如 MAPI_E_COLLISION 等相关错误（指示已尝试创建现有条目）由 **SaveChanges** 而不是 **CreateEntry 返回**。
  
## <a name="see-also"></a>另请参阅



[IABContainer::CopyEntries](iabcontainer-copyentries.md)
  
[IMAPIProp::OpenProperty](imapiprop-openproperty.md)
  
[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[PidTagCreateTemplates 规范属性](pidtagcreatetemplates-canonical-property.md)
  
[IABContainer : IMAPIContainer](iabcontainerimapicontainer.md)

