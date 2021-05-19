---
title: 跨邮件域发送
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 65594253-66cd-486a-aa5b-0bc719f761f0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ddbaa4aeacf17f2c266ccc0ff963d005f9e403ec
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410110"
---
# <a name="sending-across-messaging-domains"></a>跨邮件域发送

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
邮件域表示共享公用地址格式的一个或多个邮件系统。 跨多个邮件域的通信涉及将采用原始邮件域格式发送的邮件转换为目标邮件域的格式。 由于并非所有地址格式都兼容，因此需要网关将寻址信息从源格式转换为目标格式。 为了确保跨邮件域的有效性，客户端应用程序将重要的寻址信息存储在 MAPI 属性中。 此外，网关执行转换，检查已知需要转换的属性，并更改这些属性为目标邮件域可以使用的格式。
  
以前，MAPI 仅允许此寻址信息与组成邮件的当前收件人列表的用户相关联。 描述收件人列表每个成员的属性会不足，网关需要翻译以确保跨邮件域的有效性。 但是，某些应用程序要求其邮件包含有关用户的信息，这些用户可能是过去是收件人、将来将成为收件人或从不成为收件人。 例如，按指定顺序向一组用户发送邮件的路由应用程序在邮件中嵌入有关这些用户的寻址信息。 嵌入的信息通常包括未来收件人的地址和地址类型，可能还包括他们在路由顺序中的角色和位置、其姓名以及每个收件人的一个或多个二进制标识符。
  
为了使邮件能够包含有关这些非用户的信息，MAPI 现在包括一种策略，用于确保此非敏感信息也跨邮件域正确翻译。 此策略基于网关可映射属性的概念。
  

