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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287026"
---
# <a name="iabcontainercreateentry"></a>IABContainer::CreateEntry

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
创建一个新的条目, 该条目可以是邮件用户、通讯组列表或其他容器。
  
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
  
> 实时由_lpEntryID_参数指向的条目标识符中的字节数。 
    
 _lpEntryID_
  
> 实时一个指针, 指向用于创建特定类型的新条目的模板的条目标识符。 
    
 _ulCreateFlags_
  
> 实时用于控制如何执行条目创建的标志的位掩码。 可以设置以下标志:
    
CREATE_CHECK_DUP_LOOSE 
  
> 应执行重复项检查的松散级别。 松散重复项检查的实现是特定于提供程序的。 例如, 提供程序可以将松散匹配定义为任意两个具有相同显示名称的条目。
    
CREATE_CHECK_DUP_STRICT 
  
> 应执行严格的重复项检查级别。 严格的重复项检查实现是特定于提供程序的。 例如, 提供程序可以将一个严格的匹配定义为两个具有相同的显示名称和邮件地址的条目。
    
CREATE_REPLACE 
  
> 如果确定两个是重复的, 则新条目应替换现有条目。
    
 _lppMAPIPropEntry_
  
> 排除指向新创建的项的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功创建新条目。
    
## <a name="remarks"></a>注解

**IABContainer:: CreateEntry**方法在指定的容器中创建特定类型的新条目, 返回指向接口实现的指针, 以便进一步访问该条目。 通过使用已从其一次性表中发布的容器列表中选择的模板来创建新条目。 调用方通过调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法并请求**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性来访问容器的一次性表。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

支持**IABContainer:: CreateEntry**方法的所有容器都必须是可修改的。 在其**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) 属性中设置容器的 AB_MODIFIABLE 标志, 以指示它是可修改的。 
  
您应支持所有_ulCreateFlags_标志。 但是, 这些标志的解释和使用是特定于实现的, 也就是说, 您可以确定 CREATE_CHECK_DUP_LOOSE 和 CREATE_CHECK_DUP_STRICT 的语义在实现的上下文中的含义。 如果不能或不确定某个条目是否重复, 则始终允许创建该条目。 
  
某些提供程序通过在条目中匹配显示名称、邮件地址和搜索关键字来实现严格的条目检查。其他提供程序将匹配项限制为显示名称和地址。 通常只通过检查显示名称来实现松散条目检查。 
  
## <a name="notes-to-host-address-book-provider-implementers"></a>主机通讯簿提供程序实施者注意事项

如果您的容器可以从其他提供程序的模板中创建条目, 则**CreateEntry**的实现应为与创建的条目关联的部分或所有属性提供存储空间。 例如, 如果为条目的**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性提供存储空间, 则可以生成其详细信息对话框, 而无需依赖于外部提供程序。 
  
如果您的容器可以创建支持**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性的条目, 则您的**CreateEntry**实现必须执行以下操作: 
  
1. 调用[IMAPISupport:: OpenTemplateID](imapisupport-opentemplateid.md)方法。 **OpenTemplateID**为项启用外部提供程序的代码, 以便绑定到要创建的新项。 外部提供程序支持此绑定过程, 以保持对从其模板中创建的条目的控制, 使其成为主机通讯簿提供程序的容器。 
    
2. 执行任何必要的初始化, 并使用来自外部提供程序中的条目的所有属性填充新对象, 该对象从**OpenTemplateID**的_lppMAPIPropNew_参数中返回。
    
如果**OpenTemplateID**成功, 请将属性复制到_lppMAPIPropNew_参数所指向的实现, 而不是直接指向_lpMAPIPropData_参数指向的实现。 像对待外部提供程序中的任何其他条目一样, 初始化新条目以供脱机使用。 
  
如果**OpenTemplateID**返回一个错误, **CreateEntry**应失败。 不允许创建该条目。 由于外部提供程序可以对提供程序中的数据进行假设, 因此不要创建具有未成功绑定到外部提供程序的模板标识符的条目。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当**CreateEntry**返回时, 您可能会 (也可能不能) 立即访问新条目的条目标识符。 在您调用新条目的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法之前, 一些通讯簿提供程序不会使其可用。 
  
尽管将重复的检查标志作为参数传递给**CreateEntry**, 但在调用**SaveChanges**之前不会发生重复的检查操作。 因此, 诸如 MAPI_E_COLLISION 的相关错误 (表示试图创建已有条目) 由**SaveChanges**而不是**CreateEntry**返回。
  
## <a name="see-also"></a>另请参阅



[IABContainer::CopyEntries](iabcontainer-copyentries.md)
  
[IMAPIProp::OpenProperty](imapiprop-openproperty.md)
  
[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[PidTagCreateTemplates 规范属性](pidtagcreatetemplates-canonical-property.md)
  
[IABContainer : IMAPIContainer](iabcontainerimapicontainer.md)

