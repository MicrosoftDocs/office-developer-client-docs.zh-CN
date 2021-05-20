---
title: One-Off表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0f2040b7-9b6c-4eae-aa68-29c4f7b8bd76
description: 上次修改时间：2011 年 11 月 8 日
ms.openlocfilehash: 8719536efa9bffb1226f8fb665b912eb872227f1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439525"
---
# <a name="one-off-tables"></a>One-Off表

**适用于**：Outlook 2013 | Outlook 2016 
  
一对一表包含有关通讯簿提供程序支持用于创建新收件人的模板的信息。 一键式表由通讯簿提供程序、单个通讯簿容器和 MAPI 实现，可以是永久性的或临时的。 
  
> [!NOTE]
> 不要将一键式表中的模板与模板标识符混淆;尽管它们的用途相似，但代码构造不相似。 模板用于创建特定类型的收件人，而模板标识符用于绑定属于具有代码的宿主提供程序的某个收件人的数据，以支持属于某个外提供程序的另一个收件人。 
  
客户端创建新收件人：
  
- 添加到传出邮件的收件人列表。
    
- 添加到通讯簿中的容器之一。
    
在这两种方案中，都要求通讯簿提供程序返回一次表。 通讯簿提供程序可以实施单一一次一次表以用于这两种情况，也可以针对每种情况实现唯一的一次关闭表。 
  
当收件人将包含在传出邮件中时，MAPI 将调用通讯簿提供程序的 [IABLogon：：GetOneOffTable](iablogon-getoneofftable.md) 方法来检索其一次表。 一对一表包含的模板允许用户输入信息，从而创建具有有效地址的收件人。 MAPI 在此表上注册通知，保持其打开状态，以便用户可以反映更改。 MAPI 仅在调用其子系统或通讯簿状态对象的 [IMAPIStatus：：ValidateState](imapistatus-validatestate.md) 方法时释放该表。 
  
将收件人添加到容器时，MAPI 将进行不同的调用，调用容器的 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法来检索其 **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性。 此一式表中包含的模板集表示可添加到容器的收件人类型。 例如，邮件服务器通常会为安装的每个网关公开一个容器，以便每个容器仅保留特定于相应网关的地址。
  
MAPI 提供了一个一对一表，其中包含其自己的模板以及会话中每个通讯簿提供程序的模板。 MAPI 提供了一个通用模板，该模板可用于为任何地址类型创建新收件人（假定用户知道其格式）。 通讯簿提供程序通过调用 [IMAPISupport：：GetOneOffTable 使用此一对一表](imapisupport-getoneofftable.md)。 MAPI 一对一表中包含的每个模板都会导致创建具有有效收件人地址的收件人。
  
通讯簿提供程序通常为它们支持的每种地址类型提供一个模板。 但是，不需要对模板的支持。 不允许新建地址的通讯簿提供程序可以在 MAPI MAPI_E_NO_SUPPORT请求一次表时返回一个地址。 允许创建新地址但不提供任何模板的通讯簿提供程序可以调用 **IMAPISupport：：GetOneOffTable** 以使用 MAPI 一次关闭表中列出的模板。 
  
以下属性在一次表内设置必需的列：
  
- **PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md)) 
    
- **PR_DEPTH (** [PidTagDepth](pidtagdepth-canonical-property.md)) 
    
- **PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 
    
- **PR_DISPLAY_TYPE (** [PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 
    
- **PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md)) 
    
- **PR_INSTANCE_KEY (** [PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 
    
- **PR_SELECTABLE (** [PidTagSelectable](pidtagselectable-canonical-property.md)) 
    
 **PR_ADDRTYPE** 指示可以与使用模板创建的新收件人关联的地址类型。 
  
 **PR_DISPLAY_NAME** 和 **PR_DISPLAY_TYPE** 数据与新收件人关联。 **PR_DISPLAY_NAME** 包含一个标识新收件人的字符串，PR_DISPLAY_TYPE **一个** 常量，该常量标识要与行一起显示的图标的类型。 邮件用户的模板 **将PR_DISPLAY_TYPE列** 设置为DT_MAILUSER;通讯组列表的模板 **将PR_DISPLAY_TYPE设置为** DT_DISTLIST。 
  
 **PR_ENTRYID** 是用于创建新收件人的模板的条目标识符。 此条目标识符可以传递给将来的[IAddrBook：：NewEntry、IAddrBook：：OpenEntry](iaddrbook-newentry.md)和[IABContainer：：CreateEntry](iabcontainer-createentry.md)调用。 [](iaddrbook-openentry.md) 容器将 **默认邮件用户模板** 行的 PR_ENTRYID 列设置为 **PR_DEF_CREATE_MAILUSER** ([PidTagDefCreateMailuser](pidtagdefcreatemailuser-canonical-property.md)) ，将默认通讯组列表模板的行的 **PR_ENTRYID** 列设置为 **PR_DEF_CREATE_DL** ([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md)) 。 
  
 **PR_DEPTH** 用于通过指示模板的缩进级别来支持一次方表中的条目的分层显示。 尽管一键式表可以显示为一个简单列表或分层显示，但后者是首选的，通讯簿提供程序应该通过适当地设置每一行的 **PR_DEPTH** 列来支持它。 **PR_DEPTH** 从零开始;行中值为 0 的 **行PR_DEPTH** 不缩进。 行的缩 **进PR_DEPTH** 越小。 例如，设置为 1 PR_DEPTH行缩进一个制表位，而将 PR_DEPTH设置为 3 **的行** 则缩进三个制表位。  
  
 **PR_SELECTABLE** 用于指示表格中的行是否代表一个模板，该模板被选中并用于创建一个新收件人。 尽管一次表中的大多数行都表示模板，但提供程序可以包含非模板行。 例如，提供程序可能希望按模板类型组织一次表，包括显示在显示器中但不用于创建收件人的类别行。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

