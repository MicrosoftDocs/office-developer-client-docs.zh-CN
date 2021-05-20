---
title: 获取并设置多个属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 29b7f5f1-afc1-45d9-8867-9312c072e74b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: dd25751978eb036531238e6372e35934b3ec145a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432259"
---
# <a name="getting-and-setting-multiple-properties"></a>获取并设置多个属性

**适用于**：Outlook 2013 | Outlook 2016 
  
通过获取和设置尽可能少的调用属性，可以减少远程活动，并减少每个属性所涉及的开销。 虽然服务提供商尝试在调用远程过程以检索或修改之前收集属性，但您可以通过请求多个属性来优化此操作。
  
例如，如果您使用路由列表来描述未来具有属于特定属性集的命名属性的收件人，则使用两个呼叫处理所有收件人。 使用一次 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 调用来检索所有收件人属性的标识符，使用另一个调用 [IMAPIProp：：GetProps](imapiprop-getprops.md) 检索所有值。 或者，调用 **GetIDsFromNames，** 然后调用每个收件人的 **GetProps，** 效率要低得多。 
  

