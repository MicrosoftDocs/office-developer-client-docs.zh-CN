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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339716"
---
# <a name="sending-across-messaging-domains"></a>跨邮件域发送

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
邮件域代表共享公用地址格式的一个或多个邮件系统。 跨多个邮件域的通信需要将以原始邮件域格式发送的邮件转换为目标邮件域的格式。 因为并非所有地址格式都兼容, 所以需要一个网关将源格式的寻址信息转换为目标格式。 为了确保邮件域之间的有效性, 客户端应用程序将重要的寻址信息存储在 MAPI 属性中。 此外, 网关将执行转换, 检查已知需要转换的属性, 并将其更改为目标邮件域可以使用的格式。
  
以前, MAPI 允许仅将此寻址信息与包含邮件当前收件人列表的用户相关联。 描述收件人列表中每个成员的属性 underwent 网关所需的转换, 以确保邮件域的有效性。 但是, 有些应用程序要求其邮件包括可能是过去收件人的用户的地址信息, 以后将是收件人, 或者永远不会是收件人。 例如, 将以指定顺序向一组用户发送邮件的路由应用程序会在邮件中嵌入有关这些用户的寻址信息。 嵌入的信息通常包括将来收件人的地址和地址类型, 以及其在路由顺序中的角色和位置、它们的名称以及每个收件人的一个或多个二进制标识符。
  
若要启用邮件以包含有关这些 nonrecipient 用户的信息, MAPI 现在提供了一种策略, 用于确保在邮件域中也能正确翻译此 nonrecipient 信息。 此策略基于网关的不可映射属性的概念。
  

