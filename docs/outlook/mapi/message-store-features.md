---
title: 邮件存储功能
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d9167cd2-fc88-46b1-9a26-151955fb606c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 092cf56aea2e246fbb7ef2016a2662a1f67f889b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439518"
---
# <a name="message-store-features"></a>邮件存储功能

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
邮件存储提供程序比其他 MAPI 服务提供商更复杂，因为邮件存储提供程序可以实施更广泛的可选功能。 邮件存储提供程序所需的功能列表相当短。 但是，典型的邮件存储提供程序将支持许多可选功能，因为大多数 MAPI 客户端都非常有用或需要许多可选功能。 下表列出了邮件存储提供程序可以实现的主要功能，以及每个功能对于所有邮件存储提供程序和默认邮件存储提供程序是必需还是可选。
  
|**功能**|**全部**|**默认**|
|:-----|:-----|:-----|
|通过 MAPI 状态表提供状态。  <br/> |必需  <br/> |必需  <br/> |
|实现文件夹对象。  <br/> |必需  <br/> |必需  <br/> |
|实现 message 对象。  <br/> |必需  <br/> |必需  <br/> |
|提供已读和未读报表。  <br/> |必需  <br/> |必需  <br/> |
|提供进度接口。  <br/> |必需  <br/> |必需  <br/> |
|提供配置接口。  <br/> |必需  <br/> |必需  <br/> |
|支持表单和视图支持的关联内容表。  <br/> |可选  <br/> |可选  <br/> |
|使用邮件存储提供程序发送邮件。  <br/> |可选  <br/> |必需  <br/> |
|使用邮件存储提供程序接收邮件。  <br/> |可选  <br/> |必需  <br/> |
|支持邮件附件。  <br/> |可选  <br/> |可选  <br/> |
|支持邮件的富文本格式。  <br/> |可选  <br/> |可选  <br/> |
|提供通知。  <br/> |可选  <br/> |可选  <br/> |
|支持搜索。  <br/> |可选  <br/> |可选  <br/> |
|支持紧密耦合的邮件存储/传输提供程序。  <br/> |可选  <br/> |可选  <br/> |
|支持不重复使用条目标识符。  <br/> |可选  <br/> |可选  <br/> |
   
许多可选功能可以通过在邮件存储对象的 **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md) 属性中设置各种标志来向 MAPI 和客户端应用程序) 。 所需功能没有与其关联的标志。 **PR_STORE_SUPPORT_MASK** 邮件存储、文件夹和邮件对象上必须具有此权限。 
  
## <a name="see-also"></a>另请参阅



[开发 MAPI 邮件存储提供程序](developing-a-mapi-message-store-provider.md)

