---
title: MAPI 通讯簿
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6703ba3f-54a5-4059-b10a-1d42a9e81be1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 14f9bff8dbf55456c37e70e1ae7a0c236471b6c0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410600"
---
# <a name="mapi-address-book"></a>MAPI 通讯簿

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
集成通讯簿是 MAPI 实现的对象, 用于提供对来自配置文件中所有通讯簿提供程序的寻址信息的集成集合的访问。 通过通讯簿, 客户端应用程序和服务提供商不必区分邮件系统的唯一寻址方案。 相反, 他们可以在任何邮件系统中查找任何收件人的地址, 只要安装了邮件系统的通讯簿提供程序。
  
可以通过编程方式访问通讯簿, 无需用户干预, 也可以交互方式通过使用通用对话框。 MAPI 包括用于显示通讯簿中条目的摘要列表的对话框、有关特定收件人的详细信息, 当用户创建无法映射到唯一地址的收件人时发出警告, 以及用于创建新的模板表单的一组模板表单。发送.
  
MAPI 通讯簿在结构中类似于邮件存储区, 因为它是按层次组织的。 通讯簿提供了对由通讯簿提供程序实现的三种类型的对象的访问权限:
  
- 通讯簿容器对象。
    
- 通讯组列表对象。
    
- 消息传递用户对象。
    
通过其通讯簿提供程序分配的唯一条目标识符访问每种类型的对象。 
  
通讯簿容器类似于文件夹, 因为它们保留不同类型的对象。 通讯簿容器可以保留其他通讯簿容器以及邮件用户和通讯组列表对象。 通讯簿容器用于组织和存储通讯簿对象。
  
为了实现通讯簿的集成外观, 通讯簿提供程序向 MAPI 公开了零个、一个或多个顶级容器, 并将其合并并在一个顶级容器下显示结果。 通讯簿提供程序可以选择为一种类型的邮件会话和另一个会话的不同集公开一组容器。 通讯簿提供程序也可能没有顶级容器, 只公开可用于创建收件人的模板列表。
  
邮件收件人是通过邮件用户和通讯组列表对象实现的。 邮件传递用户是单个收件人;通讯组列表是组收件人。 每个邮件用户都有一个特定类型的唯一地址, 该地址由特定的邮件系统处理。 通讯组列表是一个已命名的收件人集合。 通讯组列表可以包含邮件传递用户对象和其他通讯组列表。 当客户端应用程序的用户将邮件发送到通讯组列表时, 该邮件将被发送到列表的每个邮件用户成员。 
  
邮件用户和通讯组列表具有一组称为基本地址属性的五个属性。 这些属性是必需的属性, 如下所示进行简要说明。
  
|**基址属性**|**说明**|
|:-----|:-----|
|**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))  <br/> |收件人的地址类型。 每种地址类型遵循一种特定的格式, 并与特定的邮件系统一起使用。  <br/> |
|**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |收件人的可显示名称。  <br/> |
|**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))  <br/> |收件人的地址。  <br/> |
|**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))  <br/> |用于访问收件人的条目标识符。  <br/> |
|**PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))  <br/> |用于标识收件人的二进制可比较密钥。  <br/> |
   
MAPI 定义了许多属性组, 它们是基址属性的变体。 这些其他组描述了不同情况下的邮件用户和通讯组列表。 例如, 一组属性描述了邮件的代理发件人和代理收件人的另一个组。
  

