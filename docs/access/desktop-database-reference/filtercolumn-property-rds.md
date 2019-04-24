---
title: FilterColumn 属性 (RDS)
TOCTitle: FilterColumn property (RDS)
ms:assetid: fb5d9f23-b62a-8131-d6ff-8b7ed8bb825c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250287(v=office.15)
ms:contentKeyID: 48548868
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d29c591c88de4b53535c26430bf369cbd3f53284
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292438"
---
# <a name="filtercolumn-property-rds"></a><span data-ttu-id="7917b-102">FilterColumn 属性 (RDS)</span><span class="sxs-lookup"><span data-stu-id="7917b-102">FilterColumn property (RDS)</span></span>

<span data-ttu-id="7917b-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="7917b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7917b-104">指示要在其中计算筛选条件的列。</span><span class="sxs-lookup"><span data-stu-id="7917b-104">Indicates the column on which to evaluate the filter criteria.</span></span>

## <a name="syntax"></a><span data-ttu-id="7917b-105">语法</span><span class="sxs-lookup"><span data-stu-id="7917b-105">Syntax</span></span>

<span data-ttu-id="7917b-106">*rds.datacontrol*。FilterColumn = *String*</span><span class="sxs-lookup"><span data-stu-id="7917b-106">*DataControl*.FilterColumn = *String*</span></span>

## <a name="parameters"></a><span data-ttu-id="7917b-107">参数</span><span class="sxs-lookup"><span data-stu-id="7917b-107">Parameters</span></span>

|<span data-ttu-id="7917b-108">参数</span><span class="sxs-lookup"><span data-stu-id="7917b-108">Parameter</span></span>|<span data-ttu-id="7917b-109">描述</span><span class="sxs-lookup"><span data-stu-id="7917b-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="7917b-110">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="7917b-110">*DataControl*</span></span> |<span data-ttu-id="7917b-111">一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="7917b-111">An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>|
|<span data-ttu-id="7917b-112">*String*</span><span class="sxs-lookup"><span data-stu-id="7917b-112">*String*</span></span> |<span data-ttu-id="7917b-p101">一个 **String** 值，指定要在其上计算筛选条件的列。筛选条件在 [FilterCriterion](filtercriterion-property-rds.md) 属性中指定。</span><span class="sxs-lookup"><span data-stu-id="7917b-p101">A **String** value that specifies the column on which to evaluate the filter criteria. The filter criteria are specified in the [FilterCriterion](filtercriterion-property-rds.md) property.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7917b-115">注解</span><span class="sxs-lookup"><span data-stu-id="7917b-115">Remarks</span></span>

<span data-ttu-id="7917b-116">[SortColumn](sortcolumn-property-rds.md)、[SortDirection](sortdirection-property-rds.md)、 [FilterValue](filtervalue-property-rds.md) 、 [FilterCriterion](filtercriterion-property-rds.md) 和 **FilterColumn** 属性提供客户端缓存的排序和筛选功能。</span><span class="sxs-lookup"><span data-stu-id="7917b-116">The [SortColumn](sortcolumn-property-rds.md), [SortDirection](sortdirection-property-rds.md), [FilterValue](filtervalue-property-rds.md), [FilterCriterion](filtercriterion-property-rds.md), and **FilterColumn** properties provide sorting and filtering functionality on the client-side cache.</span></span> 

<span data-ttu-id="7917b-117">排序功能根据某一列的值对记录进行排序。</span><span class="sxs-lookup"><span data-stu-id="7917b-117">The sorting functionality orders records by values from one column.</span></span> <span data-ttu-id="7917b-118">筛选功能根据查找条件显示记录的子集，而整个 [Recordset](recordset-object-ado.md) 则保留在缓存中。</span><span class="sxs-lookup"><span data-stu-id="7917b-118">The filtering functionality displays a subset of records based on find criteria, while the full [Recordset](recordset-object-ado.md) is maintained in the cache.</span></span> 

<span data-ttu-id="7917b-119">[Reset](reset-method-rds.md) 方法将执行条件，并用可更新的 **Recordset** 替换当前的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="7917b-119">The [Reset](reset-method-rds.md) method will execute the criteria and replace the current **Recordset** with an updatable **Recordset**.</span></span>

