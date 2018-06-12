---
title: 从表格行中检索数据
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 19a42794-a3a2-4336-af2a-473f24431252
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 91b1fa06fd47321e9c19d9751caac793e27e8f16
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778640"
---
# <a name="retrieving-data-from-table-rows"></a><span data-ttu-id="e9107-103">从表格行中检索数据</span><span class="sxs-lookup"><span data-stu-id="e9107-103">Retrieving Data from Table Rows</span></span>

  
  
<span data-ttu-id="e9107-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e9107-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e9107-105">从表中检索行包括：</span><span class="sxs-lookup"><span data-stu-id="e9107-105">Retrieving rows from a table involves:</span></span>
  
- <span data-ttu-id="e9107-106">获取所有列的属性值。</span><span class="sxs-lookup"><span data-stu-id="e9107-106">Obtaining the property values for all the columns.</span></span>
    
- <span data-ttu-id="e9107-107">修改当前的位置。</span><span class="sxs-lookup"><span data-stu-id="e9107-107">Modifying the current position.</span></span>
    
<span data-ttu-id="e9107-108">大多数表中所需的列之一是条目标识符 — **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性 — 可用于打开代表行的对象。</span><span class="sxs-lookup"><span data-stu-id="e9107-108">One of the required columns in most tables is an entry identifier — the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property — that can be used to open the object that represents the row.</span></span> <span data-ttu-id="e9107-109">此条目标识符通常为短期条目标识符，一个将不会过表的生存期。</span><span class="sxs-lookup"><span data-stu-id="e9107-109">This entry identifier is usually a short-term entry identifier, one that does not persist past the lifetime of the table.</span></span> <span data-ttu-id="e9107-110">但是，它可以是长期标识符，如果服务提供商实现表仅支持一种类型的项标识符。</span><span class="sxs-lookup"><span data-stu-id="e9107-110">However, it can be a long-term identifier if the service provider implementing the table only supports one type of entry identifier.</span></span>
  
<span data-ttu-id="e9107-111">客户端和服务提供商可以进行以下呼叫检索行之一：</span><span class="sxs-lookup"><span data-stu-id="e9107-111">Clients and service providers can make one of the following calls to retrieve rows:</span></span>
  
|||
|:-----|:-----|
|[<span data-ttu-id="e9107-112">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="e9107-112">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md) <br/> |<span data-ttu-id="e9107-113">检索指定的开头中向前或向后方向的当前行的行数。</span><span class="sxs-lookup"><span data-stu-id="e9107-113">Retrieves a specified number of rows starting with the current row in either a forward or backward direction.</span></span>  <br/> |
|[<span data-ttu-id="e9107-114">HrQueryAllRows</span><span class="sxs-lookup"><span data-stu-id="e9107-114">HrQueryAllRows</span></span>](hrqueryallrows.md) <br/> |<span data-ttu-id="e9107-115">检索所有表中的行。</span><span class="sxs-lookup"><span data-stu-id="e9107-115">Retrieves all of the rows in a table.</span></span>  <br/> |
|[<span data-ttu-id="e9107-116">ITableData::HrQueryRow</span><span class="sxs-lookup"><span data-stu-id="e9107-116">ITableData::HrQueryRow</span></span>](itabledata-hrqueryrow.md) <br/> |<span data-ttu-id="e9107-117">检索其索引列的值根据表中的行。</span><span class="sxs-lookup"><span data-stu-id="e9107-117">Retrieves a row in a table according to the value of its index column.</span></span> <span data-ttu-id="e9107-118">**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 通常是表的索引列。</span><span class="sxs-lookup"><span data-stu-id="e9107-118">**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) is usually the index column for a table.</span></span>  <br/> |
   
<span data-ttu-id="e9107-119">可选属性，包含作为一个表中的列时，某些行时其他人也可能不，可能有列的有效值。</span><span class="sxs-lookup"><span data-stu-id="e9107-119">When an optional property is included as one of the columns in a table, some of the rows might have valid values for the column while others might not.</span></span> <span data-ttu-id="e9107-120">一个有效的值是否存在列取决于是否提供行的信息的对象设置属性。</span><span class="sxs-lookup"><span data-stu-id="e9107-120">Whether a valid value exists for a column depends on whether the object providing the information for the row sets the property.</span></span> <span data-ttu-id="e9107-121">根据对象的实现，不存在属性可以表示为**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) 表或任意值中。</span><span class="sxs-lookup"><span data-stu-id="e9107-121">Depending on the implementation of the object, a non-existent property can be represented in the table as **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) or an arbitrary value.</span></span> <span data-ttu-id="e9107-122">必须注意区分属性不存在且具有无意义的值和属性存在且具有有效的值的表的用户。</span><span class="sxs-lookup"><span data-stu-id="e9107-122">Users of tables must be careful to differentiate between properties that are nonexistent and have meaningless values and properties that do exist and have valid values.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e9107-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9107-123">See also</span></span>



[<span data-ttu-id="e9107-124">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="e9107-124">MAPI Tables</span></span>](mapi-tables.md)

