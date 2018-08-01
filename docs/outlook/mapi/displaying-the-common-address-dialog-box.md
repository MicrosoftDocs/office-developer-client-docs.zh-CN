---
title: 显示“常用地址”对话框
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 276f9fa8-c333-4381-b20f-22fe9d2f27cd
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a7b603504956be9ec3066e5ff5e1d5db7d59852a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774830"
---
# <a name="displaying-the-common-address-dialog-box"></a>显示“常用地址”对话框

  
  
**适用于**： Outlook 
  
MAPI 常见地址对话框中可用于各种寻址的任务，如构建收件人列表。 若要显示此对话框中，调用**IAddrBook::Address**。 根据您设置的许多参数和如何设置，您可以从特定的容器，您显示对特定类型的条目限制。
  
 **若要限制到显示个人通讯簿 (PAB) 条目地址对话框**
  
1. 调用[IAddrBook::GetPAB](iaddrbook-getpab.md)检索 PAB 的项标识符。 
    
2. 创建作为[SPropertyRestriction](spropertyrestriction.md)结构和**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 或**PR_AB_PROVIDER_ID** ([PidTagAbProviderId](pidtagabproviderid-canonical-property.md)) 的**relop**成员使用 RELOP_EQ 属性限制**ulPropTag**成员。 如果您使用**PR_ENTRYID**，通过从**GetPAB**检索的项标识符。 如果您使用**PR_AB_PROVIDER_ID**，传递 MSPAB 中包含的值。H 头文件。 **PR_AB_PROVIDER_ID**是 PAB 设计的 MAPI 的唯一标识符。 
    
3. 使用指向属性限制_lpHierRestriction_参数调用[IAddrBook::Address](iaddrbook-address.md) 。 
    

