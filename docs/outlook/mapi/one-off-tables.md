---
title: 一次性表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0f2040b7-9b6c-4eae-aa68-29c4f7b8bd76
description: '上次修改时间: 2011 年11月8日'
ms.openlocfilehash: 8719536efa9bffb1226f8fb665b912eb872227f1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439525"
---
# <a name="one-off-tables"></a>一次性表

**适用于**：Outlook 2013 | Outlook 2016 
  
一次性表格包含有关通讯簿提供程序为创建新收件人所支持的模板的信息。 一次性表格由通讯簿提供程序、单独的通讯簿容器和 MAPI 实现, 并且可以是持久的或临时的。 
  
> [!NOTE]
> 请勿将一次性表格中的模板与模板标识符混淆;尽管它们的目的是相似的, 但其代码构造不是什么相似。 模板用于创建特定类型的收件人, 而模板标识符用于绑定属于主机提供程序的一个收件人的数据, 以支持属于外部提供程序的另一个收件人。 
  
客户端创建新的收件人:
  
- 添加到传出邮件的收件人列表中。
    
- 添加到通讯簿中的某个容器。
    
在这两种情况下, 都要求通讯簿提供程序返回一个一次性表格。 通讯簿提供程序可以实现在这两种情况下使用一个一次性表, 也可以在每种情况下使用唯一的一次性表。 
  
当收件人将包含在传出邮件中时, MAPI 会调用通讯簿提供程序的[IABLogon:: GetOneOffTable](iablogon-getoneofftable.md)方法来检索其一次性表。 一次性表格包含模板, 使用户可以输入信息, 从而创建具有有效地址的收件人。 此表上的通知的 MAPI 寄存器, 使其保持打开状态, 以便可以将更改反映到用户。 只有在调用其子系统或通讯簿状态对象的[IMAPIStatus:: ValidateState](imapistatus-validatestate.md)方法时, MAPI 才会释放该表。 
  
将收件人添加到容器中时, MAPI 将发出不同的调用, 调用容器的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法检索其**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性。 此一次性表格中包含的模板集代表可添加到容器中的收件人的类型。 例如, 邮件服务器通常会为每个已安装的网关公开一个容器, 以便每个容器仅保留特定于相应网关的地址。
  
MAPI 提供了一个一次性表格, 其中包含自己的模板以及会话中每个通讯簿提供程序中的模板。 MAPI 提供了一个通用模板, 可用于为任何地址类型创建新的收件人, 假定用户知道其格式。 通讯簿提供程序通过调用[IMAPISupport:: GetOneOffTable](imapisupport-getoneofftable.md)来使用此一次性表格。 MAPI 一次性表中包含的每个模板都将创建具有有效收件人地址的收件人。
  
通讯簿提供程序通常为其支持的每种地址类型提供一个模板。 但是, 不需要对模板的支持。 当 MAPI 调用请求一次性表时, 不允许创建新地址的通讯簿提供程序可能会返回 MAPI_E_NO_SUPPORT。 允许创建新地址但不提供任何模板的通讯簿提供程序可以调用**IMAPISupport:: GetOneOffTable**以使用 MAPI 一次性表中列出的模板。 
  
以下属性构成了一次性表中所需的列集:
  
- **PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))
    
- **PR_DEPTH**([PidTagDepth](pidtagdepth-canonical-property.md))
    
- **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
    
- **PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))
    
- **PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))
    
- **PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))
    
- **PR_SELECTABLE**([PidTagSelectable](pidtagselectable-canonical-property.md))
    
 **PR_ADDRTYPE**指示可与使用模板创建的新收件人相关联的地址类型。 
  
 **PR_DISPLAY_NAME**和**PR_DISPLAY_TYPE**将数据与新的收件人相关联。 **PR_DISPLAY_NAME**包含一个标识新的收件人和**PR_DISPLAY_TYPE**的字符串, 该字符串包含一个常量, 用于标识要与行一起显示的图标的类型。 邮件用户的模板将其 " **PR_DISPLAY_TYPE** " 列设置为 "DT_MAILUSER"。通讯组列表的模板将其**PR_DISPLAY_TYPE**列设置为 DT_DISTLIST。 
  
 **PR_ENTRYID**是要用于创建新收件人的模板的条目标识符。 此条目标识符可传递给未来的[IAddrBook:: NewEntry](iaddrbook-newentry.md), [IAddrBook:: OpenEntry](iaddrbook-openentry.md), and [IABContainer:: CreateEntry](iabcontainer-createentry.md) calls。 容器将默认邮件用户模板的行的**PR_ENTRYID**列设置为**PR_DEF_CREATE_MAILUSER** ([PidTagDefCreateMailuser](pidtagdefcreatemailuser-canonical-property.md)), 并将其行的**PR_ENTRYID**列设置为默认的通讯组列表模板到**PR_DEF_CREATE_DL** ([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md))。 
  
 **PR_DEPTH**用于通过指示模板的缩进级别来支持一次性表格中的条目的分层显示。 虽然一次性表可以显示为简单列表或层次结构显示, 但后者是首选的, 通讯簿提供程序应通过相应地为每行设置**PR_DEPTH**列来支持这两个表。 **PR_DEPTH**是从零开始的;**PR_DEPTH**列中值为0的行不缩进。 **PR_DEPTH**的值越大, 缩进的行越多。 例如, 将**PR_DEPTH**设置为1的行会缩进一个制表符, 而**PR_DEPTH**设置为3的行缩进三个选项卡。 
  
 **PR_SELECTABLE**用于指示表中的行是否表示可选择并用于创建新收件人的模板。 尽管一次性表格中的大多数行都代表模板, 但提供程序可以包含非模板行。 例如, 提供商可能希望按模板类型组织一次性表格, 包括显示在显示中但不用于创建收件人的类别行。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

