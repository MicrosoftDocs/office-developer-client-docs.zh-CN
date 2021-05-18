---
title: 从表行检索数据
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 19a42794-a3a2-4336-af2a-473f24431252
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2f389d26ec80b9af3ed28c5eb85b589c9cbb26c5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405252"
---
# <a name="retrieving-data-from-table-rows"></a><span data-ttu-id="90d1e-103">从表行检索数据</span><span class="sxs-lookup"><span data-stu-id="90d1e-103">Retrieving Data from Table Rows</span></span>

  
  
<span data-ttu-id="90d1e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="90d1e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="90d1e-105">从表中检索行涉及：</span><span class="sxs-lookup"><span data-stu-id="90d1e-105">Retrieving rows from a table involves:</span></span>
  
- <span data-ttu-id="90d1e-106">获取所有列的属性值。</span><span class="sxs-lookup"><span data-stu-id="90d1e-106">Obtaining the property values for all the columns.</span></span>
    
- <span data-ttu-id="90d1e-107">修改当前位置。</span><span class="sxs-lookup"><span data-stu-id="90d1e-107">Modifying the current position.</span></span>
    
<span data-ttu-id="90d1e-108">大多数表中所需的列之一是条目标识符 **（PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性）可用于打开表示该行的对象。</span><span class="sxs-lookup"><span data-stu-id="90d1e-108">One of the required columns in most tables is an entry identifier — the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property — that can be used to open the object that represents the row.</span></span> <span data-ttu-id="90d1e-109">此条目标识符通常是一个短期条目标识符，一个不会在表的生存期之后仍然保留的标识符。</span><span class="sxs-lookup"><span data-stu-id="90d1e-109">This entry identifier is usually a short-term entry identifier, one that does not persist past the lifetime of the table.</span></span> <span data-ttu-id="90d1e-110">但是，如果实现表的服务提供商仅支持一种类型的条目标识符，则它可以是长期标识符。</span><span class="sxs-lookup"><span data-stu-id="90d1e-110">However, it can be a long-term identifier if the service provider implementing the table only supports one type of entry identifier.</span></span>
  
<span data-ttu-id="90d1e-111">客户端和服务提供商可以进行以下调用之一来检索行：</span><span class="sxs-lookup"><span data-stu-id="90d1e-111">Clients and service providers can make one of the following calls to retrieve rows:</span></span>
  
|||
|:-----|:-----|
|[<span data-ttu-id="90d1e-112">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="90d1e-112">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md) <br/> |<span data-ttu-id="90d1e-113">以向前或向后方向检索以当前行开始指定的行数。</span><span class="sxs-lookup"><span data-stu-id="90d1e-113">Retrieves a specified number of rows starting with the current row in either a forward or backward direction.</span></span>  <br/> |
|[<span data-ttu-id="90d1e-114">HrQueryAllRows</span><span class="sxs-lookup"><span data-stu-id="90d1e-114">HrQueryAllRows</span></span>](hrqueryallrows.md) <br/> |<span data-ttu-id="90d1e-115">检索表中的所有行。</span><span class="sxs-lookup"><span data-stu-id="90d1e-115">Retrieves all of the rows in a table.</span></span>  <br/> |
|[<span data-ttu-id="90d1e-116">ITableData::HrQueryRow</span><span class="sxs-lookup"><span data-stu-id="90d1e-116">ITableData::HrQueryRow</span></span>](itabledata-hrqueryrow.md) <br/> |<span data-ttu-id="90d1e-117">根据索引列的值检索表格中的行。</span><span class="sxs-lookup"><span data-stu-id="90d1e-117">Retrieves a row in a table according to the value of its index column.</span></span> <span data-ttu-id="90d1e-118">**PR_INSTANCE_KEY (** [PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 通常是表的索引列。</span><span class="sxs-lookup"><span data-stu-id="90d1e-118">**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) is usually the index column for a table.</span></span>  <br/> |
   
<span data-ttu-id="90d1e-119">当可选属性作为表中的列之一包含时，一些行可能具有该列的有效值，而其他行可能没有。</span><span class="sxs-lookup"><span data-stu-id="90d1e-119">When an optional property is included as one of the columns in a table, some of the rows might have valid values for the column while others might not.</span></span> <span data-ttu-id="90d1e-120">列是否存在有效值取决于提供行信息的对象是否设置属性。</span><span class="sxs-lookup"><span data-stu-id="90d1e-120">Whether a valid value exists for a column depends on whether the object providing the information for the row sets the property.</span></span> <span data-ttu-id="90d1e-121">根据对象的实现，表中不存在的属性可以表示为 PR_NULL ([PidTagNull](pidtagnull-canonical-property.md) ) 或任意值。</span><span class="sxs-lookup"><span data-stu-id="90d1e-121">Depending on the implementation of the object, a non-existent property can be represented in the table as **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) or an arbitrary value.</span></span> <span data-ttu-id="90d1e-122">表的用户必须小心区分不存在、具有无意义的值和具有有效值的属性。</span><span class="sxs-lookup"><span data-stu-id="90d1e-122">Users of tables must be careful to differentiate between properties that are nonexistent and have meaningless values and properties that do exist and have valid values.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="90d1e-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90d1e-123">See also</span></span>



[<span data-ttu-id="90d1e-124">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="90d1e-124">MAPI Tables</span></span>](mapi-tables.md)

