---
title: XML 中的记录集动态属性
TOCTitle: Recordset Dynamic Properties in XML
ms:assetid: 6ee1f176-9986-4ade-fc97-e3dad8e6bc6b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249439(v=office.15)
ms:contentKeyID: 48545522
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4193220e450c59e7293ed6befa37d8da23801f27
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465860"
---
# <a name="recordset-dynamic-properties-in-xml"></a><span data-ttu-id="342f7-102">XML 中的记录集动态属性</span><span class="sxs-lookup"><span data-stu-id="342f7-102">Recordset Dynamic Properties in XML</span></span>


<span data-ttu-id="342f7-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="342f7-103">**Applies to**: Access 2013 | Office 2013</span></span>

## <a name="recordset-dynamic-properties-in-xml"></a><span data-ttu-id="342f7-104">XML 中的记录集动态属性</span><span class="sxs-lookup"><span data-stu-id="342f7-104">Recordset Dynamic Properties in XML</span></span>

<span data-ttu-id="342f7-105">以下特定于提供程序的 **Recordset** 属性（从客户端游标引擎）目前会持久化到 XML 格式中：</span><span class="sxs-lookup"><span data-stu-id="342f7-105">The following **Recordset** provider-specific properties (from the Client Cursor Engine) are currently persisted into the XML format:</span></span>

  - <span data-ttu-id="342f7-106">**Update Resync**</span><span class="sxs-lookup"><span data-stu-id="342f7-106">**Update Resync**</span></span>

  - <span data-ttu-id="342f7-107">**Unique Table**</span><span class="sxs-lookup"><span data-stu-id="342f7-107">**Unique Table**</span></span>

  - <span data-ttu-id="342f7-108">**Unique Schema**</span><span class="sxs-lookup"><span data-stu-id="342f7-108">**Unique Schema**</span></span>

  - <span data-ttu-id="342f7-109">**Unique Catalog**</span><span class="sxs-lookup"><span data-stu-id="342f7-109">**Unique Catalog**</span></span>

  - <span data-ttu-id="342f7-110">**Resync Command**</span><span class="sxs-lookup"><span data-stu-id="342f7-110">**Resync Command**</span></span>

  - <span data-ttu-id="342f7-111">**IRowsetChange**</span><span class="sxs-lookup"><span data-stu-id="342f7-111">**IRowsetChange**</span></span>

  - <span data-ttu-id="342f7-112">**IRowsetUpdate**</span><span class="sxs-lookup"><span data-stu-id="342f7-112">**IRowsetUpdate**</span></span>

  - <span data-ttu-id="342f7-113">**CommandTimeout**</span><span class="sxs-lookup"><span data-stu-id="342f7-113">**CommandTimeout**</span></span>

  - <span data-ttu-id="342f7-114">**BatchSize**</span><span class="sxs-lookup"><span data-stu-id="342f7-114">**BatchSize**</span></span>

  - <span data-ttu-id="342f7-115">**UpdateCriteria**</span><span class="sxs-lookup"><span data-stu-id="342f7-115">**UpdateCriteria**</span></span>

  - <span data-ttu-id="342f7-116">**Reshape Name**</span><span class="sxs-lookup"><span data-stu-id="342f7-116">**Reshape Name**</span></span>

  - <span data-ttu-id="342f7-117">**AutoRecalc**</span><span class="sxs-lookup"><span data-stu-id="342f7-117">**AutoRecalc**</span></span>

<span data-ttu-id="342f7-p101">这些属性将作为正在持久化的 **Recordset** 的元素定义的属性保存在架构节中。这些属性是在行集架构命名空间中定义的，并且必须有前缀"rs:"。</span><span class="sxs-lookup"><span data-stu-id="342f7-p101">These properties are saved in the schema section as attributes of the element definition for the **Recordset** being persisted. These attributes are defined in the rowset schema namespace and must have the prefix "rs:".</span></span>

