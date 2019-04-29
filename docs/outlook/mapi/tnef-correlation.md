---
title: TNEF 关联
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 93d1716d-a0be-45aa-85d2-6c9be65f5fd2
description: 上次修改时间：2013 年 3 月 12 日
ms.openlocfilehash: 8d601bb2bbc65e21c5bc83179cc29e53ddd33876
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410369"
---
# <a name="tnef-correlation"></a>TNEF 关联

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
某些邮件系统会对附加到入站邮件的任何传输中性封装格式 (TNEF) 流执行关联检查, 以验证 TNEF 流实际上是否属于该邮件。 这涉及将入站邮件标头中某个字段的值与在 TNEF 流的某些属性中存储的值的副本相匹配。 对于每个邮件, (例如邮件 ID 号) 的值应是唯一的, 因此通常使用这些值。 创建 TNEF 流的传输或网关负责从邮件头中选择适当的值, 并在将传出邮件的属性编码到 TNEF 流中之前将副本放入相应的属性中。 接收邮件的网关或传输可以从 TNEF 流中提取该属性, 并验证其值是否与入站邮件中对应的头字段的值相匹配。
  
如果值不匹配, 网关或传输应丢弃 TNEF 流, 并且仅处理本机邮件信封。 这种检查非常谨慎, 因为基于非 MAPI 的邮件客户端可能会将包含 TNEF 流的文件从旧邮件附加到转发邮件或甚至不相关的邮件中。如果未选中, 则此类错误可能导致丢失邮件文本。
  
所选的标头字段值必须对邮件是唯一的。 没有针对所有邮件系统的固定标头字段, 因为不同的邮件系统使用不同的标头字段, 但通常邮件系统会将唯一标识符分配给适合此目的的邮件。 例如, SMTP 系统通常使用 MessageID 头, 而 x-blade 系统通常使用 IM_THIS_IPM 属性。
  

