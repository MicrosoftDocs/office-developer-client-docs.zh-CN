---
title: 表定位
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a0cbbc93-8074-4e86-b660-ee7bab910587
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 656f696c58e9b62e7e601d7f531870b8c385e862
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345652"
---
# <a name="table-positioning"></a><span data-ttu-id="b4ee3-103">表定位</span><span class="sxs-lookup"><span data-stu-id="b4ee3-103">Table Positioning</span></span>

  
  
<span data-ttu-id="b4ee3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b4ee3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b4ee3-105">表中的当前位置始终由游标指示。</span><span class="sxs-lookup"><span data-stu-id="b4ee3-105">The current position within a table is always indicated by a cursor.</span></span> <span data-ttu-id="b4ee3-106">对于表的每个视图, 都有一个游标;它的值由表的实施者设置。</span><span class="sxs-lookup"><span data-stu-id="b4ee3-106">There is one cursor for each view of a table; its value is set by the table's implementer.</span></span> <span data-ttu-id="b4ee3-107">当使用表的客户端或服务提供程序进行调用以更改表的位置时, 游标的值将重置。</span><span class="sxs-lookup"><span data-stu-id="b4ee3-107">When a client or service provider using the table makes a call to change the position of the table, the value of the cursor is reset.</span></span> <span data-ttu-id="b4ee3-108">可以通过以下方式更改表的位置:</span><span class="sxs-lookup"><span data-stu-id="b4ee3-108">A table's position can be changed with:</span></span>
  
- <span data-ttu-id="b4ee3-109">书签。</span><span class="sxs-lookup"><span data-stu-id="b4ee3-109">A bookmark.</span></span>
    
- <span data-ttu-id="b4ee3-110">小数值。</span><span class="sxs-lookup"><span data-stu-id="b4ee3-110">A fractional value.</span></span>
    
- <span data-ttu-id="b4ee3-111">一个筛选器。</span><span class="sxs-lookup"><span data-stu-id="b4ee3-111">A filter.</span></span>
    

