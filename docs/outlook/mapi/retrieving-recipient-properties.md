---
title: 检索收件人属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 358f892b-54a7-4213-b3c0-94f28f99716f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 38063cebe70b153decce6713ac5fc31d6916dbf6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426672"
---
# <a name="retrieving-recipient-properties"></a>检索收件人属性
  
**适用于**：Outlook 2013 | Outlook 2016 
  
### <a name="to-access-one-or-more-properties-of-an-address-book-entry"></a>访问通讯簿条目的一个或多个属性
  
1. 对于每个感兴趣的通讯簿条目，调用 [IAddrBook：：OpenEntry，](iaddrbook-openentry.md)传递目标邮件用户或通讯组列表的条目标识符。
    
2. 然后执行下列操作之一：
    
   - 使用要检索的一个或多个属性的列表，为感兴趣的每个通讯簿条目调用消息传送用户或通讯组列表的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法。 
    
   - 调用 [IAddrBook：:P repareRecips](iaddrbook-preparerecips.md)，传递包含所有所需通讯簿条目的所有属性的 [ADRLIST](adrlist.md) 结构。 由于一次 **调用 PrepareRecips** 可能会返回多个通讯簿条目的信息，因此当您对多个收件人感兴趣时，这是首选策略。 
    

