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
ms.openlocfilehash: a26701b5b0f9f31277a442321e5e3016cfcb4d1e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776505"
---
# <a name="message-store-features"></a>邮件存储区功能

  
  
**适用于**： Outlook 
  
消息存储提供程序是比其他 MAPI 服务提供商更复杂的这是的消息存储提供程序具有更广泛的可选它们可以实现的功能。 相当简短消息存储提供程序所需的功能的列表。 但是，典型的消息存储提供程序将支持大量的可选功能，因为的许多可选功能都非常有用或必需的大多数 MAPI 客户端。 下表列出了消息存储提供程序可以实现和每个功能是否必需或可选的所有消息存储提供程序和默认消息存储提供程序的主要功能。
  
|**功能**|**All**|**Default**|
|:-----|:-----|:-----|
|MAPI 状态表中提供状态。  <br/> |必需  <br/> |必需  <br/> |
|实现文件夹对象。  <br/> |必需  <br/> |必需  <br/> |
|实现消息对象。  <br/> |必需  <br/> |必需  <br/> |
|提供读取和 nonread 报告。  <br/> |必需  <br/> |必需  <br/> |
|提供进度接口。  <br/> |必需  <br/> |必需  <br/> |
|提供配置界面。  <br/> |必需  <br/> |必需  <br/> |
|表单和视图支持关联的内容表。  <br/> |可选  <br/> |可选  <br/> |
|发送邮件的邮件存储提供程序。  <br/> |可选  <br/> |必需  <br/> |
|消息存储提供程序接收消息。  <br/> |可选  <br/> |必需  <br/> |
|支持邮件附件。  <br/> |可选  <br/> |可选  <br/> |
|支持的邮件的富文本格式。  <br/> |可选  <br/> |可选  <br/> |
|提供通知。  <br/> |可选  <br/> |可选  <br/> |
|支持搜索。  <br/> |可选  <br/> |可选  <br/> |
|支持紧密耦合消息存储/传输提供程序。  <br/> |可选  <br/> |可选  <br/> |
|支持非重复使用的项标识符。  <br/> |可选  <br/> |可选  <br/> |
   
多个可选功能可以被播发到 MAPI，并通过设置各种标志邮件中的客户端应用程序存储对象的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性。 所需的功能不具有与其关联的标志。 消息存储库、 文件夹和消息对象上需要**PR_STORE_SUPPORT_MASK** 。 
  
## <a name="see-also"></a>另请参阅



[开发 MAPI 邮件存储区提供程序](developing-a-mapi-message-store-provider.md)

