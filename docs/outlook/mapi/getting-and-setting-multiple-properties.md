---
title: 获取和设置多个属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 29b7f5f1-afc1-45d9-8867-9312c072e74b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 88c3e0bdb3cc6660e35faf62c5bb63ec2f6352bc
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590370"
---
# <a name="getting-and-setting-multiple-properties"></a>获取和设置多个属性

**适用于**： Outlook 2013 |Outlook 2016 
  
获取和设置尽可能使用最少的多个属性的呼叫，远程 curtailed 活动并减少了开销涉及与每个属性数。 尽管服务提供商尝试进行远程过程调用的检索或修改之前收集属性，您可以通过首先请求多个属性来优化这项成果。
  
例如，如果您使用路由描述将来收件人属于特定的属性集的命名属性的列表，可处理所有的收件人的两个通话。 一次调用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)用于检索所有收件人的属性和其他调用[IMAPIProp::GetProps](imapiprop-getprops.md)以检索的所有值的标识符。 或者，对于每个收件人后, 跟**GetProps**调用**GetIDsFromNames**调用是效率显著降低。 
  

