---
title: TNEF 相关性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 93d1716d-a0be-45aa-85d2-6c9be65f5fd2
description: 上次修改时间： 2013 年 3 月 12 日
ms.openlocfilehash: b8b30dcc2fcf0c8e75004e36b6fd9f4f4583e304
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778983"
---
# <a name="tnef-correlation"></a>TNEF 相关性

 
  
**适用于**： Outlook 
  
某些消息系统执行任何连接到验证 TNEF 流确实实际上属于该邮件的入站消息的传输中性封装格式 (TNEF) 流相关检查。 此步骤需要使用 TNEF 流中的某些属性中存储的值的一个副本的入站邮件头中某些字段的值相匹配。 值可能是唯一的每条消息，如消息 ID 号，通常用于此。 传输或网关创建 TNEF 流负责为从邮件标头中选择适当的值和放置到 TNEF 流编码传出消息的属性之前复制到一个合适的属性。 网关或收到消息的传输可以从 TNEF 流提取属性并验证其值匹配的入站邮件上的相应标头字段值。
  
如果值不匹配，则应放弃的网关或传输的 TNEF 流和处理仅本机邮件信封。 此类检查都谨慎，因为不基于 MAPI 的邮件客户端可能将附加包含从旧的邮件转发或甚至无关的消息; TNEF 流的文件如果未选中，这样的错误可能导致丢失的消息文本。
  
所选的标头字段的值必须是唯一的邮件。 因为不同邮件系统使用不同的页眉字段，则没有固定标头字段的所有邮件系统，但消息系统通常分配给适用于此目的的邮件的唯一标识符。 例如，SMTP 系统通常使用 MessageID 标头，而 X.400 系统通常使用 IM_THIS_IPM 属性。
  

