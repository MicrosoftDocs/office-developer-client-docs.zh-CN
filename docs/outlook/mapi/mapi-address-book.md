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
ms.openlocfilehash: de63e728fbabf9c153f7a4faa68cad1d7a9331ec
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587920"
---
# <a name="mapi-address-book"></a>MAPI 通讯簿

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
集成的通讯簿是 MAPI 实现以提供从配置文件中的地址簿提供程序的所有访问寻址信息集成集合的对象。 通讯簿中，使用客户端应用程序和服务提供商不必区分消息系统的唯一的寻址方案。 相反，它们可查找任何收件人的地址在任何消息系统中，只要安装在邮件系统通讯簿提供程序。
  
无需用户干预，或以交互方式使用通用对话框可以以编程方式访问通讯簿。 MAPI 包括在通讯簿，特定收件人，当用户创建的收件人，无法映射到唯一的地址和一套将表单模板创建新的警告的详细信息中显示的项的摘要列表的对话框收件人。
  
MAPI 通讯簿的消息存储结构类似，在于层次结构组织。 通讯簿提供了三种类型的通讯簿提供程序实现的对象的访问：
  
- 通讯簿容器对象。
    
- 通讯组列表对象。
    
- 消息的用户对象。
    
每个这些类型的对象来访问其分配由其地址簿提供程序的唯一项标识符。 
  
通讯簿容器是类似于文件夹的这是的它们保存不同类型的对象。 通讯簿容器可以保留其他通讯簿容器以及消息用户和通讯组列表对象。 通讯簿容器用于组织和存储通讯簿对象。
  
若要获得通讯簿的集成的外观，通讯簿提供程序公开零、 一个或多个为其将它们合并，并显示单个的顶级容器下结果的 MAPI 其顶级容器。 通讯簿提供程序可以选择要公开的一种类型的另一个会话的邮件会话和一组不同的容器的一组。 还有可能地址簿提供商已没有顶级容器和公开仅可用于创建收件人的模板的列表。
  
邮件的收件人，实现与邮件用户和通讯组列表对象。 消息的用户是单个收件人;通讯组列表是组收件人。 每个邮件用户具有特定的消息系统处理的特定类型的唯一的地址。 通讯组列表是收件人的命名的集合。 通讯组列表可以包含消息的用户对象和其他通讯组列表。 当客户端应用程序的用户将一条消息发送到通讯组列表时，邮件被发送到每个列表的邮件用户的成员。 
  
邮件用户和通讯组列表具有一组称为基址属性的五个属性。 这些是必需的属性，并简要描述，如下所示。
  
|**基址属性**|**说明**|
|:-----|:-----|
|**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))  <br/> |收件人地址的类型。 每个地址类型遵循特定的格式，并使用与特定的邮件系统。  <br/> |
|**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |收件人的可显示名称。  <br/> |
|**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))  <br/> |收件人地址。  <br/> |
|**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))  <br/> |用于访问收件人的项标识符。  <br/> |
|**PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))  <br/> |用于标识的收件人的二进制相当键。  <br/> |
   
MAPI 定义多组变体的基址属性的属性。 邮件用户和通讯组列表在不同情况下，介绍了这些其他组。 例如，一组属性描述了一条消息和其他组委托收件人的代理人发件人。
  

