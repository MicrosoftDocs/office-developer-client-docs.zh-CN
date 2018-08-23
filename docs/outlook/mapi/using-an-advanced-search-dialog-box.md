---
title: 使用“高级搜索”对话框
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c9a156e6-3472-4409-a4ba-3a1a65b7bdcd
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 581607e184d67413e735c4cbfb874643b3222a80
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588767"
---
# <a name="using-an-advanced-search-dialog-box"></a>使用“高级搜索”对话框

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
一些地址簿容器支持高级搜索功能，允许客户端搜索之外**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 的属性。 支持高级的搜索的通讯簿容器具有名为**PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) 的容器对象属性。 此容器对象提供对介绍搜索对话框中显示表访问 — 用于输入和编辑高级的搜索条件的对话框。
  
 **对通讯簿容器执行高级的搜索**
  
1. 调用容器的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法，指定**PR_SEARCH**属性标记和 IID_IMAPIContainer 接口标识符。 
    
2. 调用 search 对象的**IMAPIProp::OpenProperty**方法，该接口的标识符的属性标记和 IID_IMAPITable 指定**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md))。 
    
3. 调用 search 对象的[IMAPIProp::SetProps](imapiprop-setprops.md)方法来建立在高级搜索中使用的属性值。 
    
4. 调用 search 对象的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法，以保存高级的搜索条件。 
    
调用此顺序将导致时搜索对象的**GetSearchCriteria**方法在客户端调用的限制。 
  

