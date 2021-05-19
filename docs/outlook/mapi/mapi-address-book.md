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
  
集成通讯簿是 MAPI 实现的对象，用于提供对来自配置文件中所有通讯簿提供程序的寻址信息的集成集合的访问。 对于通讯簿，客户端应用程序和服务提供商不需要区分邮件系统的唯一寻址方案。 相反，只要安装了邮件系统的通讯簿提供程序，他们就可以查找任何邮件系统中任何收件人的地址。
  
通讯簿可通过编程方式访问，无需用户干预，或者使用公用对话框以交互方式访问。 MAPI 包括用于显示通讯簿中条目的摘要列表、有关特定收件人的详细信息、用户创建无法映射到唯一地址的收件人时显示的警告以及一组用于创建新收件人的模板表单的对话框。
  
MAPI 通讯簿的结构类似于邮件存储，因为它按层次结构进行组织。 通讯簿提供对通讯簿提供程序实现的三种类型的对象的访问：
  
- 通讯簿容器对象。
    
- 通讯组列表对象。
    
- 消息传递用户对象。
    
通过通讯簿提供程序分配的唯一条目标识符可以访问每种类型的对象。 
  
通讯簿容器类似于文件夹，因为它们包含不同类型的对象。 通讯簿容器可以容纳其他通讯簿容器以及邮件用户和通讯组列表对象。 通讯簿容器用于组织和存储通讯簿对象。
  
为了实现通讯簿的集成外观，通讯簿提供程序向 MAPI 公开零个、一个或多个顶级容器，MAPI 将合并这些容器，并显示单个顶级容器下的结果。 通讯簿提供程序可以选择为一种类型的邮件会话公开一组容器，为另一个会话公开另一组容器。 通讯簿提供程序也可能没有顶级容器，并且只能公开可用于创建收件人的模板列表。
  
邮件收件人通过邮件用户和通讯组列表对象实现。 邮件用户是单个收件人;通讯组列表是组收件人。 每个邮件用户都有一个特定邮件系统处理的特定类型的唯一地址。 通讯组列表是收件人的命名集合。 通讯组列表可以包含邮件用户对象和其他通讯组列表。 当客户端应用程序的用户向通讯组列表发送邮件时，邮件将发送给该列表的每个邮件用户成员。 
  
邮件用户和通讯组列表具有一组称为基本地址属性的五个属性。 这些是必需属性，并简要说明如下。
  
|**基地址属性**|**说明**|
|:-----|:-----|
|**PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md))   <br/> |收件人的地址类型。 每个地址类型都遵循特定格式，并用于特定的邮件系统。  <br/> |
|**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md))   <br/> |收件人的可显示名称。  <br/> |
|**PR_EMAIL_ADDRESS (** [PidTagEmailAddress)](pidtagemailaddress-canonical-property.md)  <br/> |收件人的地址。  <br/> |
|**PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md))   <br/> |用于访问收件人的条目标识符。  <br/> |
|**PR_SEARCH_KEY (** [PidTagSearchKey](pidtagsearchkey-canonical-property.md))   <br/> |用于标识收件人的二进制比较键。  <br/> |
   
MAPI 定义许多作为基本地址属性变体的属性组。 这些其他组描述了不同情况下的邮件用户和通讯组列表。 例如，一组属性描述邮件的代理发件人，另一组描述委派收件人。
  

