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
  
通过使用最少的调用数获取和设置尽可能多的属性, 远程活动是 curtailed 的, 并且降低每个属性所需的开销。 虽然服务提供程序在进行远程过程调用以进行检索或修改之前尝试收集属性, 但您可以通过请求使用多个属性开始来优化这一工作。
  
例如, 如果您使用的路由列表描述了具有属于特定属性集的命名属性的后续收件人, 请处理两个呼叫的所有收件人。 使用一个调用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)检索所有收件人属性的标识符, 以及对[IMAPIProp:: GetProps](imapiprop-getprops.md)的其他调用, 以检索所有值。 另一种方法是, 在调用**GetIDsFromNames**后, 对每个收件人调用**GetProps** , 效率要低得多。 
  

