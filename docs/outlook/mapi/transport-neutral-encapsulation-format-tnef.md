---
title: 传输中性封装格式 (TNEF)
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 98d4fe3c-3908-4cd2-bfdb-ff1874a80b24
description: 上次修改时间： 2013 年 3 月 12 日
ms.openlocfilehash: 440c27b019b91ec8c2c02e37850d2768a273559b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591931"
---
# <a name="transport-neutral-encapsulation-format-tnef"></a>传输中性封装格式 (TNEF)

 
  
**适用于**： Outlook 2013 |Outlook 2016 
  
TNEF 是用于转换的 MAPI 属性集的格式 — MAPI 邮件 — 到串行数据流。 由传输提供程序需要进行编码通过不直接支持这些属性的消息系统传输的 MAPI 邮件属性主要用于 TNEF 函数。 例如，基于 SMTP 传输使用 TNEF 编码属性类似**PR_SENT_REPRESENTING_NAME** ([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))，其结构中的 SMTP 邮件没有直接的表示形式。
  
TNEF 实现定义多个特定于 TNEF 的属性，其中每个对应于特定的 MAPI 属性。 这些属性用于编码到 TNEF 流及其各自的 MAPI 属性。 此外，定义特殊属性可用于封装不具有特定属性对应于其任何 MAPI 属性。 这些属性定义的原因，而不是只需使用统一的编码的所有 MAPI 属性的方法 — 是启用向后兼容的非 MAPI 兼容的软件正在使用 TNEF。
  
本节的其余部分介绍的结构和 TNEF 流，MAPI 属性和 TNEF 属性和重要注意事项某些 TNEF 属性之间的映射的语法。
  

