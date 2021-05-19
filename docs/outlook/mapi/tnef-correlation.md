---
title: TNEF 相关性
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
# <a name="tnef-correlation"></a>TNEF 相关性

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
某些邮件系统对附加到入站邮件的任何 Transport-Neutral 封装格式 (TNEF) 流执行相关检查，以验证 TNEF 流实际上是否属于该邮件。 这包括将入站邮件头中某些字段的值与存储在 TNEF 流中的某些属性中的该值的副本进行匹配。 通常，对于每封邮件唯一的值（如邮件 ID 号）通常用于此。 创建 TNEF 流的传输或网关负责从邮件头选择一个合适的值，在将传出邮件的属性编码到 TNEF 流之前，将副本放入相应的属性中。 然后，接收邮件的网关或传输可以从 TNEF 流中提取该属性并验证其值是否与入站邮件上相应头字段的值匹配。
  
如果值不匹配，网关或传输应丢弃 TNEF 流并仅处理本机邮件信封。 此类检查是谨慎的，因为非基于 MAPI 的邮件客户端可能会将包含 TNEF 流的文件从旧邮件附加到转发，甚至是不相关的邮件;如果未选中，则此类错误可能导致邮件文本丢失。
  
选择的邮件头字段值必须是唯一的。 所有邮件系统没有固定的邮件头字段，因为不同的邮件系统使用不同的头字段，但通常邮件系统为邮件分配一个适合此目的的唯一标识符。 例如，SMTP 系统通常使用 MessageID 标头，而 X.400 系统通常使用 IM_THIS_IPM 属性。
  

