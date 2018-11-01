---
title: FilterColumn 属性 (RDS)
TOCTitle: FilterColumn Property (RDS)
ms:assetid: fb5d9f23-b62a-8131-d6ff-8b7ed8bb825c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250287(v=office.15)
ms:contentKeyID: 48548868
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9cf03a2cbff06919981ac940f5b2962062a850c2
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25877798"
---
# <a name="filtercolumn-property-rds"></a><span data-ttu-id="4b550-102">FilterColumn 属性 (RDS)</span><span class="sxs-lookup"><span data-stu-id="4b550-102">FilterColumn Property (RDS)</span></span>


<span data-ttu-id="4b550-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4b550-103">**Applies to**: Access 2013, Office 2013</span></span>



<span data-ttu-id="4b550-104">指示要在其中计算筛选条件的列。</span><span class="sxs-lookup"><span data-stu-id="4b550-104">Indicates the column on which to evaluate the filter criteria.</span></span>

## <a name="syntax"></a><span data-ttu-id="4b550-105">语法</span><span class="sxs-lookup"><span data-stu-id="4b550-105">Syntax</span></span>

<span data-ttu-id="4b550-106">*DataControl*。FilterColumn =*字符串*</span><span class="sxs-lookup"><span data-stu-id="4b550-106">*DataControl*.FilterColumn = *String*</span></span>

## <a name="parameters"></a><span data-ttu-id="4b550-107">参数</span><span class="sxs-lookup"><span data-stu-id="4b550-107">Parameters</span></span>

  - <span data-ttu-id="4b550-108">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="4b550-108">*DataControl*</span></span>

  - <span data-ttu-id="4b550-109">一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="4b550-109">An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>

  - <span data-ttu-id="4b550-110">*String*</span><span class="sxs-lookup"><span data-stu-id="4b550-110">*String*</span></span>

  - <span data-ttu-id="4b550-p101">一个 **String** 值，指定要在其上计算筛选条件的列。筛选条件在 [FilterCriterion](filtercriterion-property-rds.md) 属性中指定。</span><span class="sxs-lookup"><span data-stu-id="4b550-p101">A **String** value that specifies the column on which to evaluate the filter criteria. The filter criteria are specified in the [FilterCriterion](filtercriterion-property-rds.md) property.</span></span>

## <a name="remarks"></a><span data-ttu-id="4b550-113">备注</span><span class="sxs-lookup"><span data-stu-id="4b550-113">Remarks</span></span>

<span data-ttu-id="4b550-p102">[SortColumn](sortcolumn-property-rds.md)、 [SortDirection](sortdirection-property-rds.md) 、 [FilterValue](filtervalue-property-rds.md)、[FilterCriterion](filtercriterion-property-rds.md) 和 **FilterColumn** 属性提供客户端缓存的排序和筛选功能。排序功能根据某一列的值对记录进行排序。筛选功能根据查找条件显示记录的子集，而整个 [Recordset](recordset-object-ado.md) 则保留在缓存中。 [Reset](reset-method-rds.md) 方法将执行条件，并用可更新的 **Recordset** 替换当前的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="4b550-p102">The [SortColumn](sortcolumn-property-rds.md), [SortDirection](sortdirection-property-rds.md), [FilterValue](filtervalue-property-rds.md), [FilterCriterion](filtercriterion-property-rds.md), and **FilterColumn** properties provide sorting and filtering functionality on the client-side cache. The sorting functionality orders records by values from one column. The filtering functionality displays a subset of records based on find criteria, while the full [Recordset](recordset-object-ado.md) is maintained in the cache. The [Reset](reset-method-rds.md) method will execute the criteria and replace the current **Recordset** with an updatable **Recordset**.</span></span>

