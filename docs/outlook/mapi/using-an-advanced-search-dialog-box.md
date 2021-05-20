---
title: 使用高级搜索对话框
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c9a156e6-3472-4409-a4ba-3a1a65b7bdcd
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 70b62eeaf6e737747c98b3abcd6e7053f71d4308
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437299"
---
# <a name="using-an-advanced-search-dialog-box"></a>使用高级搜索对话框

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
某些通讯簿容器支持高级搜索功能，该功能允许客户端搜索[PidTagDisplayName](pidtagdisplayname-canonical-property.md) PR_DISPLAY_NAME (属性) 。  支持高级搜索的通讯簿容器具有名为 PR_SEARCH ( [PidTagSearch](pidtagsearch-canonical-property.md)) 。 此容器对象提供对描述搜索对话框（用于输入和编辑高级搜索条件的对话框）的显示表的访问。
  
 **对通讯簿容器执行高级搜索**
  
1. 调用容器的[IMAPIProp：：OpenProperty](imapiprop-openproperty.md)方法，PR_SEARCH属性标记指定值，IID_IMAPIContainer指定接口标识符。 
    
2. 调用搜索对象的 **IMAPIProp：：OpenProperty** 方法，为属性标记指定 **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) ，为接口标识符指定 IID_IMAPITable。 
    
3. 调用搜索对象的 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法，为要用于高级搜索的属性建立值。 
    
4. 调用搜索对象的 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法来保存高级搜索条件。 
    
此调用序列导致在客户端调用搜索对象的 **GetSearchCriteria** 方法时可用的限制。 
  

