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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: acf9cee9bf0713b909b0d82fc606b015ac28474e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775223"
---
# <a name="iabcontainercreateentry"></a>IABContainer::CreateEntry

  
  
**适用于**： Outlook 
  
创建一个新项，可以是邮件用户、 通讯组列表或其他容器。
  
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
  
> [in]中_lpEntryID_参数指向的项标识符的字节数。 
    
 _lpEntryID_
  
> [in]指向用于创建特定类型的新条目的模板的项标识符的指针。 
    
 _ulCreateFlags_
  
> [in]位掩码的标志控制如何执行项创建的。 可以设置以下标志：
    
CREATE_CHECK_DUP_LOOSE 
  
> 应执行的重复项检查松散级别。 提供程序特定的松散重复项检查实现。 例如，提供程序可以定义松散匹配项，如任何具有相同的两个条目的显示名称。
    
CREATE_CHECK_DUP_STRICT 
  
> 应执行的重复项检查严格级别。 提供程序特定的严格的重复项检查实现。 例如，提供程序可以定义严格匹配项，如任何具有两个相同的两个条目显示名称和消息地址。
    
CREATE_REPLACE 
  
> 如果确定两个是重复项，新条目应替换现有。
    
 _lppMAPIPropEntry_
  
> [输出]为指向新创建的项的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功创建新条目。
    
## <a name="remarks"></a>说明

**IABContainer::CreateEntry**方法会返回一个指针接口实现进一步访问该条目指定容器中创建特定类型的新条目。 使用已发布其一次性表中的可用模板的容器的列表中选择一个模板创建新条目。 呼叫者通过调用其[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法并请求**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性来访问容器的一次性表。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

所有容器都支持**IABContainer::CreateEntry**方法必须都进行修改。 指示可修改其**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) 属性中设置您的容器 AB_MODIFIABLE 标志。 
  
您应支持的所有_ulCreateFlags_标志。 但是，解释和使用这些标志是实现特定 — 即，您可以确定 CREATE_CHECK_DUP_LOOSE 和 CREATE_CHECK_DUP_STRICT 的语义实现的上下文中的含义。 如果您不能或不确定条目是否重复，始终允许创建的条目。 
  
某些提供程序实现严格条目匹配的显示名称，检查消息地址和中条目; 搜索键其他提供程序限制显示名称和地址匹配。 通常，通过检查的显示名称实现松散条目检查。 
  
## <a name="notes-to-host-address-book-provider-implementers"></a>承载通讯簿提供程序实施者说明

如果您的容器可以从其他提供程序的模板创建条目， **CreateEntry**的实现应提供存储为部分或全部与创建条目关联的属性。 例如，如果您提供存储条目**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性，则可以而无需依赖于外的提供程序生成其详细信息对话框。 
  
如果您的容器，可以创建支持**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性的条目的**CreateEntry**实现必须执行以下操作： 
  
1. 调用[IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md)方法。 **OpenTemplateID**使外提供程序的代码要绑定到正在创建的新条目的条目。 外的提供程序支持此绑定进程控制通过其模板创建到主机地址簿提供程序的容器的条目。 
    
2. 执行任何必要的初始化，并填充的所有属性从项目中的外的提供程序从**OpenTemplateID** _lppMAPIPropNew_参数中返回的对象的新对象。
    
如果**OpenTemplateID**成功，则将属性复制_lppMAPIPropNew_参数指向的实现，而不是直接向_lpMAPIPropData_参数指向的实现。 初始化脱机使用的新条目，就像外提供程序的任何其他项。 
  
如果**OpenTemplateID**返回一个错误， **CreateEntry**应该会失败。 不允许创建的条目。 因为外的提供程序可以使数据作出假设您的提供商，不要创建一个条目具有不到外的提供程序成功绑定的模板标识符。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当**CreateEntry**返回时，则可能或可能无法立即访问新条目的项标识符。 某些通讯簿提供程序后，不要做出它才可用以前呼叫过该新条目[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法。 
  
尽管重复检查标志作为参数传递给**CreateEntry**，直到调用**SaveChanges**不会发生复制检查操作。 因此，返回的**SaveChanges** ，而不是**CreateEntry**MAPI_E_COLLISION，这表明尝试创建现有条目，如相关的错误。
  
## <a name="see-also"></a>另请参阅



[IABContainer::CopyEntries](iabcontainer-copyentries.md)
  
[IMAPIProp::OpenProperty](imapiprop-openproperty.md)
  
[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[PidTagCreateTemplates 规范属性](pidtagcreatetemplates-canonical-property.md)
  
[IABContainer : IMAPIContainer](iabcontainerimapicontainer.md)

