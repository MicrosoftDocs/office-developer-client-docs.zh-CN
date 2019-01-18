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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28711782"
---
# <a name="filtercolumn-property-rds"></a><span data-ttu-id="fb5b0-102">FilterColumn 属性 (RDS)</span><span class="sxs-lookup"><span data-stu-id="fb5b0-102">FilterColumn property (RDS)</span></span>

<span data-ttu-id="fb5b0-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="fb5b0-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="fb5b0-104">指示要在其中计算筛选条件的列。</span><span class="sxs-lookup"><span data-stu-id="fb5b0-104">Indicates the column on which to evaluate the filter criteria.</span></span>

## <a name="syntax"></a><span data-ttu-id="fb5b0-105">语法</span><span class="sxs-lookup"><span data-stu-id="fb5b0-105">Syntax</span></span>

<span data-ttu-id="fb5b0-106">*DataControl*。FilterColumn =*字符串*</span><span class="sxs-lookup"><span data-stu-id="fb5b0-106">*DataControl*.FilterColumn = *String*</span></span>

## <a name="parameters"></a><span data-ttu-id="fb5b0-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="fb5b0-107">Parameters</span></span>

|<span data-ttu-id="fb5b0-108">参数</span><span class="sxs-lookup"><span data-stu-id="fb5b0-108">Parameter</span></span>|<span data-ttu-id="fb5b0-109">说明</span><span class="sxs-lookup"><span data-stu-id="fb5b0-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="fb5b0-110">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="fb5b0-110">*DataControl*</span></span> |<span data-ttu-id="fb5b0-111">一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="fb5b0-111">An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>|
|<span data-ttu-id="fb5b0-112">*String*</span><span class="sxs-lookup"><span data-stu-id="fb5b0-112">*String*</span></span> |<span data-ttu-id="fb5b0-p101">一个 **String** 值，指定要在其上计算筛选条件的列。筛选条件在 [FilterCriterion](filtercriterion-property-rds.md) 属性中指定。</span><span class="sxs-lookup"><span data-stu-id="fb5b0-p101">A **String** value that specifies the column on which to evaluate the filter criteria. The filter criteria are specified in the [FilterCriterion](filtercriterion-property-rds.md) property.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fb5b0-115">备注</span><span class="sxs-lookup"><span data-stu-id="fb5b0-115">Remarks</span></span>

<span data-ttu-id="fb5b0-116">[SortColumn](sortcolumn-property-rds.md)、[SortDirection](sortdirection-property-rds.md)、[FilterValue](filtervalue-property-rds.md)、[FilterCriterion](filtercriterion-property-rds.md) 和 **FilterColumn** 属性提供了对客户端缓存进行排序和筛选的功能。</span><span class="sxs-lookup"><span data-stu-id="fb5b0-116">The [SortColumn](sortcolumn-property-rds.md), [SortDirection](sortdirection-property-rds.md), [FilterValue](filtervalue-property-rds.md), [FilterCriterion](filtercriterion-property-rds.md), and **FilterColumn** properties provide sorting and filtering functionality on the client-side cache.</span></span> 

<span data-ttu-id="fb5b0-117">排序功能根据某一列的值对记录进行排序。</span><span class="sxs-lookup"><span data-stu-id="fb5b0-117">The sorting functionality orders records by values from one column.</span></span> <span data-ttu-id="fb5b0-118">筛选功能根据查找条件显示记录的子集，而整个 [Recordset](recordset-object-ado.md) 则保留在缓存中。</span><span class="sxs-lookup"><span data-stu-id="fb5b0-118">The filtering functionality displays a subset of records based on find criteria, while the full [Recordset](recordset-object-ado.md) is maintained in the cache.</span></span> 

<span data-ttu-id="fb5b0-119">[Reset](reset-method-rds.md) 方法将执行条件，并用可更新的 **Recordset** 替换当前的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="fb5b0-119">The [Reset](reset-method-rds.md) method will execute the criteria and replace the current **Recordset** with an updatable **Recordset**.</span></span>

