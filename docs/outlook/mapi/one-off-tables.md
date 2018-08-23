---
title: 一次性表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0f2040b7-9b6c-4eae-aa68-29c4f7b8bd76
description: 上次修改时间： 2011 年 11 月 8 日
ms.openlocfilehash: fc8d8d53dcbc091df98ba9e23533e4138660c8e2
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574564"
---
# <a name="one-off-tables"></a>一次性表

**适用于**： Outlook 2013 |Outlook 2016 
  
一次性表包含有关用于创建新的收件人的地址簿提供程序支持的模板的信息。 一次性表按通讯簿提供程序，单个地址簿容器和 MAPI，实现，并且可以是永久或临时。 
  
> [!NOTE]
> 请勿将混淆一次性模板标识符; 表中的模板其目的相似时，其代码构造是之类 nothing。 模板用于创建特定类型的收件人，而模板标识符用于将数据绑定的一个收件人属于代码的宿主提供程序以支持另一个收件人属于外的提供程序。 
  
客户端创建新的收件人：
  
- 若要添加到的传出邮件的收件人列表。
    
- 若要添加到某个通讯簿中的容器。
    
在这两种方案中，通讯簿提供程序被请求返回一次性表。 一个一次性表用于同时的情况下或唯一一次性表对于每种情况，可以实现通讯簿提供程序。 
  
当收件人将包含在传出 message 时，MAPI 调用通讯簿提供程序的[IABLogon::GetOneOffTable](iablogon-getoneofftable.md)方法来检索其一次性表。 一次性表包含模板，它使用户能够输入有效的地址与收件人的创建过程中生成的信息。 此表中，使其保持上的通知的 MAPI register 打开，以便更改可以反映到用户。 仅当调用其子系统或地址簿状态对象的[IMAPIStatus::ValidateState](imapistatus-validatestate.md)方法时，MAPI 释放表。 
  
当收件人将添加到容器时，MAPI 调用不同，调用容器的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法来检索其**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性。 模板包括在此一次性表组表示可以添加到容器的收件人的类型。 例如，邮件服务器通常公开一个容器以便每个容器仅包含地址特定于相应的网关安装每个网关。
  
MAPI 提供了一次性的会话中包括自己模板以及从通讯簿提供程序的每个模板表。 MAPI 提供了可用于创建一个新收件人的任何地址类型，假定用户知道其格式的泛型模板。 通讯簿提供程序通过调用[IMAPISupport::GetOneOffTable](imapisupport-getoneofftable.md)使用此一次性表。 每个中创建具有有效的收件人地址的收件人的 MAPI 一次性表结果中包含的模板。
  
通讯簿提供程序通常提供一个模板的它们支持每个地址类型。 但是，支持的模板，则不需要。 MAPI 呼叫请求一次性表时，不允许创建的新地址的地址簿提供程序可以返回 MAPI_E_NO_SUPPORT。 通讯簿提供程序的执行允许创建新的地址，但不是提供任何模板可以调用**IMAPISupport::GetOneOffTable**使用 MAPI 一次性表中列出的模板。 
  
以下属性构成一次性表中所需的列：
  
- **PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))
    
- **PR_DEPTH**([PidTagDepth](pidtagdepth-canonical-property.md))
    
- **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
    
- **PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))
    
- **PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))
    
- **PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))
    
- **PR_SELECTABLE**([PidTagSelectable](pidtagselectable-canonical-property.md))
    
 **PR_ADDRTYPE**指示可以使用模板创建新收件人与相关联的地址的类型。 
  
 **PR_DISPLAY_NAME**和**PR_DISPLAY_TYPE**将数据与新收件人关联。 **PR_DISPLAY_NAME**包含的字符串标识新的收件人，并且**PR_DISPLAY_TYPE**包含一个标识图标显示时带有行的类型的常量。 邮件用户的模板已设置为 DT_MAILUSER; 其**PR_DISPLAY_TYPE**列通讯组列表的模板已设置为 DT_DISTLIST 其**PR_DISPLAY_TYPE**列。 
  
 **PR_ENTRYID**是要用于创建一个新收件人的模板的项标识符。 此条目标识符可以传递给将来[IAddrBook::NewEntry](iaddrbook-newentry.md)、 [IAddrBook::OpenEntry](iaddrbook-openentry.md)和[IABContainer::CreateEntry](iabcontainer-createentry.md)呼叫。 容器设置为默认的邮件用户模板与**PR_DEF_CREATE_MAILUSER** ([PidTagDefCreateMailuser](pidtagdefcreatemailuser-canonical-property.md)) 和**PR_ENTRYID**列中的默认通讯组列表及其行及其行的**PR_ENTRYID**列到**PR_DEF_CREATE_DL** ([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md)) 模板。 
  
 **PR_DEPTH**用于支持一次性表中的条目的分层显示，通过指示的模板的缩进级别。 尽管一次性表可以显示为平面列表或分层显示，后者是最好和通讯簿提供程序应支持它的适当地设置每个行的**PR_DEPTH**列。 **PR_DEPTH**是从零开始;值为 0，在其**PR_DEPTH**列中的行不缩进。 **PR_DEPTH**的值越高的更多行是缩进。 例如，具有**PR_DEPTH**设置为 1 行是缩进一个制表时**PR_DEPTH**设置为 3 行缩进的三个选项卡。 
  
 **PR_SELECTABLE**用于指示表中的行是否表示可以选择和用于创建一个新收件人的模板。 尽管大多数一次性表中行执行代表模板，提供程序可以包括非模板行。 例如，提供程序可能需要组织一次性表按模板类型，包括在显示但不能用于收件人创建的类别行。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

