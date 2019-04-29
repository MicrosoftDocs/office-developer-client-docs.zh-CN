---
title: 使用筛选器设置表位置
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0d66124b-a018-4db4-b55b-a0e5ed467e14
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6b21d6746baf438af438787d966d9af886d4a74f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425468"
---
# <a name="setting-a-table-position-with-a-filter"></a><span data-ttu-id="a7d8c-103">使用筛选器设置表位置</span><span class="sxs-lookup"><span data-stu-id="a7d8c-103">Setting a Table Position with a Filter</span></span>

  
  
<span data-ttu-id="a7d8c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a7d8c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a7d8c-105">表用户可以将光标移动到与一组筛选条件相匹配的行。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-105">Table users can move the cursor to a row that matches a set of filter criteria.</span></span> <span data-ttu-id="a7d8c-106">筛选器可以基于各种准则, 如列属性值、位掩码或子数据子数据。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-106">Filters can be based on a variety of guidelines such as column property values, bitmasks, or subobjects.</span></span> <span data-ttu-id="a7d8c-107">使用[SRestriction](srestriction.md)结构在 MAPI 中指定筛选器。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-107">Filters are specified in MAPI using an [SRestriction](srestriction.md) structure.</span></span> 
  
 <span data-ttu-id="a7d8c-108">**将表定位到与限制中建立的条件相匹配的第一行**</span><span class="sxs-lookup"><span data-stu-id="a7d8c-108">**To position a table to the first row that matches the criteria established in a restriction**</span></span>
  
- <span data-ttu-id="a7d8c-109">调用[IMAPITable:: FindRow](imapitable-findrow.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-109">Call the [IMAPITable::FindRow](imapitable-findrow.md) method.</span></span> <span data-ttu-id="a7d8c-110">从特定书签表示的行开始, **FindRow**搜索向前或向后方向, 以定位与限制中指定的条件匹配的行。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-110">Starting with the row represented by a particular bookmark, **FindRow** searches in either a forward or backward direction to locate a row that matches the criteria specified in the restriction.</span></span> <span data-ttu-id="a7d8c-111">**FindRow**可用于实现基于字符字符串 (而不是小数值) 的滚动条。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-111">**FindRow** can be useful for implementing a scroll bar that is based on character strings, instead of fractional values.</span></span> <span data-ttu-id="a7d8c-112">例如, 在搜索集成通讯簿以启用用户 (通过输入一个或多个字符以查找以指定字符开头的名字) 时, 客户端可以调用 MAPI 的**FindRow**实现。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-112">For example, a client can call MAPI's implementation of **FindRow** when searching through the integrated address book to enable a user, by entering one or more characters, to locate the first name that begins with the specified characters.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="a7d8c-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7d8c-113">See also</span></span>



[<span data-ttu-id="a7d8c-114">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="a7d8c-114">MAPI Tables</span></span>](mapi-tables.md)

