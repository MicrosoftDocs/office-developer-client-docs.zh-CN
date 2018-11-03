---
title: XML 中的记录集动态属性
TOCTitle: Recordset dynamic properties in XML
ms:assetid: 6ee1f176-9986-4ade-fc97-e3dad8e6bc6b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249439(v=office.15)
ms:contentKeyID: 48545522
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 36069ec0e8e9020bc70ef1ea72ce25f4461c6487
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946956"
---
# <a name="recordset-dynamic-properties-in-xml"></a><span data-ttu-id="133ae-102">XML 中的记录集动态属性</span><span class="sxs-lookup"><span data-stu-id="133ae-102">Recordset dynamic properties in XML</span></span>

<span data-ttu-id="133ae-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="133ae-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="133ae-104">以下特定于提供程序的 **Recordset** 属性（从客户端游标引擎）目前会持久化到 XML 格式中：</span><span class="sxs-lookup"><span data-stu-id="133ae-104">The following **Recordset** provider-specific properties (from the Client Cursor Engine) are currently persisted into the XML format:</span></span>

- <span data-ttu-id="133ae-105">**AutoRecalc**</span><span class="sxs-lookup"><span data-stu-id="133ae-105">**AutoRecalc**</span></span>
- <span data-ttu-id="133ae-106">**BatchSize**</span><span class="sxs-lookup"><span data-stu-id="133ae-106">**BatchSize**</span></span>
- <span data-ttu-id="133ae-107">**CommandTimeout**</span><span class="sxs-lookup"><span data-stu-id="133ae-107">**CommandTimeout**</span></span>
- <span data-ttu-id="133ae-108">**IRowsetChange**</span><span class="sxs-lookup"><span data-stu-id="133ae-108">**IRowsetChange**</span></span>
- <span data-ttu-id="133ae-109">**IRowsetUpdate**</span><span class="sxs-lookup"><span data-stu-id="133ae-109">**IRowsetUpdate**</span></span>
- <span data-ttu-id="133ae-110">**Reshape Name**</span><span class="sxs-lookup"><span data-stu-id="133ae-110">**Reshape Name**</span></span>
- <span data-ttu-id="133ae-111">**Resync Command**</span><span class="sxs-lookup"><span data-stu-id="133ae-111">**Resync Command**</span></span>
- <span data-ttu-id="133ae-112">**Unique Catalog**</span><span class="sxs-lookup"><span data-stu-id="133ae-112">**Unique Catalog**</span></span>
- <span data-ttu-id="133ae-113">**Unique Schema**</span><span class="sxs-lookup"><span data-stu-id="133ae-113">**Unique Schema**</span></span>
- <span data-ttu-id="133ae-114">**Unique Table**</span><span class="sxs-lookup"><span data-stu-id="133ae-114">**Unique Table**</span></span>
- <span data-ttu-id="133ae-115">**Update Resync**</span><span class="sxs-lookup"><span data-stu-id="133ae-115">**Update Resync**</span></span>
- <span data-ttu-id="133ae-116">**UpdateCriteria**</span><span class="sxs-lookup"><span data-stu-id="133ae-116">**UpdateCriteria**</span></span>


<span data-ttu-id="133ae-p101">这些属性将作为正在持久化的 **Recordset** 的元素定义的属性保存在架构节中。这些属性是在行集架构命名空间中定义的，并且必须有前缀"rs:"。</span><span class="sxs-lookup"><span data-stu-id="133ae-p101">These properties are saved in the schema section as attributes of the element definition for the **Recordset** being persisted. These attributes are defined in the rowset schema namespace and must have the prefix "rs:".</span></span>

## <a name="see-also"></a><span data-ttu-id="133ae-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="133ae-119">See also</span></span>

- [<span data-ttu-id="133ae-120">ADO 动态属性</span><span class="sxs-lookup"><span data-stu-id="133ae-120">ADO dynamic properties</span></span>](ado-dynamic-properties.md)