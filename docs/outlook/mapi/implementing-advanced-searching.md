---
title: 实现高级搜索
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 08cc60d4-cac8-4ba5-bd7f-a56e63697be3
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 35d41ff903c5ed22c5210adf6448dfded0afe4b6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407387"
---
# <a name="implementing-advanced-searching"></a>实现高级搜索

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
某些通讯簿容器支持高级搜索功能，该功能允许客户端搜索[PidTagDisplayName](pidtagdisplayname-canonical-property.md) PR_DISPLAY_NAME (属性) 。  若要支持高级搜索，提供程序必须实现一个可通过其他容器的 **PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) 访问的特殊容器。 **PR_SEARCH** 容器对象，该对象提供对显示表的访问，该显示表描述用于输入和编辑高级搜索条件的对话框。 
  
 **支持高级搜索**
  
1. 为每个搜索条件定义一个属性。
    
2. 在容器的 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法（用于处理 PR_SEARCH 属性 **）** 中： 
    
1. 检查客户端是否正在请求 **IMAPIContainer** 接口。 如果请求的接口不正确，则失败并返回MAPI_E_INTERFACE_NOT_SUPPORTED。 
    
2. 创建支持 **IMAPIContainer 接口的新搜索** 对象。 
    
3. 此时，将调用搜索容器 **的 IMAPIProp：：OpenProperty** 方法来检索其 **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性。 提供程序必须提供显示表，通常通过调用 [BuildDisplayTable](builddisplaytable.md)来描述容器的高级搜索对话框。
    
4. MAPI 显示搜索对话框，允许用户输入相应的条件。 用户完成后，MAPI 将调用容器的 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法来存储搜索条件。 
    
5. 将进行调用以请求搜索容器的内容表。 使用与条件匹配的容器中的所有条目填充内容表。
    

