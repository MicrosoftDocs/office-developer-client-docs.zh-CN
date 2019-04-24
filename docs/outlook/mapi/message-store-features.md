---
title: 邮件存储区功能
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d9167cd2-fc88-46b1-9a26-151955fb606c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 092cf56aea2e246fbb7ef2016a2662a1f67f889b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356901"
---
# <a name="message-store-features"></a>邮件存储区功能

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
邮件存储提供程序比其他 MAPI 服务提供程序更复杂的是, 邮件存储提供程序提供了可实施的更广泛的可选功能。 邮件存储提供程序所需功能的列表相当短。 但是, 典型的邮件存储提供程序将支持许多可选功能, 因为很多可选功能非常有用, 或者大多数 MAPI 客户端都是必需的。 下表列出了邮件存储提供程序可以实现的主要功能, 以及每个功能是否为所有邮件存储提供程序和默认邮件存储提供程序都是必需的还是可选的。
  
|**功能**|**All**|**Default**|
|:-----|:-----|:-----|
|提供 MAPI 状态表的状态。  <br/> |必需  <br/> |必需  <br/> |
|实现 folder 对象。  <br/> |必需  <br/> |必需  <br/> |
|实现 message 对象。  <br/> |必需  <br/> |必需  <br/> |
|提供已读和未读报表。  <br/> |必需  <br/> |必需  <br/> |
|提供进度接口。  <br/> |必需  <br/> |必需  <br/> |
|提供配置接口。  <br/> |必需  <br/> |必需  <br/> |
|支持表单和视图支持关联的内容表。  <br/> |可选  <br/> |可选  <br/> |
|使用邮件存储提供程序发送邮件。  <br/> |可选  <br/> |必需  <br/> |
|使用邮件存储提供程序接收邮件。  <br/> |可选  <br/> |必需  <br/> |
|支持邮件附件。  <br/> |可选  <br/> |可选  <br/> |
|支持邮件的 rtf 格式。  <br/> |可选  <br/> |可选  <br/> |
|提供通知。  <br/> |可选  <br/> |可选  <br/> |
|支持搜索。  <br/> |可选  <br/> |可选  <br/> |
|支持紧密结合的邮件存储/传输提供程序。  <br/> |可选  <br/> |可选  <br/> |
|支持不重复使用条目标识符。  <br/> |可选  <br/> |可选  <br/> |
   
通过在邮件存储对象的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中设置各种标志, 可以将许多可选功能公布到 MAPI 和客户端应用程序中。 所需的功能没有与之关联的标志。 **PR_STORE_SUPPORT_MASK**对邮件存储、文件夹和邮件对象是必需的。 
  
## <a name="see-also"></a>另请参阅



[开发 MAPI 邮件存储提供程序](developing-a-mapi-message-store-provider.md)

