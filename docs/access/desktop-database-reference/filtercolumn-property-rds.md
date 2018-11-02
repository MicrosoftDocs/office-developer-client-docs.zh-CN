---
title: FilterColumn 属性 (RDS)
TOCTitle: FilterColumn property (RDS)
ms:assetid: fb5d9f23-b62a-8131-d6ff-8b7ed8bb825c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250287(v=office.15)
ms:contentKeyID: 48548868
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c3c9f20b26ff184bcd3f1a24f7f1523acdc5f184
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25927387"
---
# <a name="filtercolumn-property-rds"></a><span data-ttu-id="e307f-102">FilterColumn 属性 (RDS)</span><span class="sxs-lookup"><span data-stu-id="e307f-102">FilterColumn property (RDS)</span></span>


<span data-ttu-id="e307f-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e307f-103">**Applies to**: Access 2013, Office 2013</span></span>



<span data-ttu-id="e307f-104">指示要在其中计算筛选条件的列。</span><span class="sxs-lookup"><span data-stu-id="e307f-104">Indicates the column on which to evaluate the filter criteria.</span></span>

## <a name="syntax"></a><span data-ttu-id="e307f-105">语法</span><span class="sxs-lookup"><span data-stu-id="e307f-105">Syntax</span></span>

<span data-ttu-id="e307f-106">*DataControl*。FilterColumn =*字符串*</span><span class="sxs-lookup"><span data-stu-id="e307f-106">*DataControl*.FilterColumn = *String*</span></span>

## <a name="parameters"></a><span data-ttu-id="e307f-107">参数</span><span class="sxs-lookup"><span data-stu-id="e307f-107">Parameters</span></span>

  - <span data-ttu-id="e307f-108">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="e307f-108">*DataControl*</span></span>

  - <span data-ttu-id="e307f-109">一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="e307f-109">An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>

  - <span data-ttu-id="e307f-110">*String*</span><span class="sxs-lookup"><span data-stu-id="e307f-110">*String*</span></span>

  - <span data-ttu-id="e307f-p101">一个 **String** 值，指定要在其上计算筛选条件的列。筛选条件在 [FilterCriterion](filtercriterion-property-rds.md) 属性中指定。</span><span class="sxs-lookup"><span data-stu-id="e307f-p101">A **String** value that specifies the column on which to evaluate the filter criteria. The filter criteria are specified in the [FilterCriterion](filtercriterion-property-rds.md) property.</span></span>

## <a name="remarks"></a><span data-ttu-id="e307f-113">备注</span><span class="sxs-lookup"><span data-stu-id="e307f-113">Remarks</span></span>

<span data-ttu-id="e307f-p102">[SortColumn](sortcolumn-property-rds.md)、 [SortDirection](sortdirection-property-rds.md) 、 [FilterValue](filtervalue-property-rds.md)、[FilterCriterion](filtercriterion-property-rds.md) 和 **FilterColumn** 属性提供客户端缓存的排序和筛选功能。排序功能根据某一列的值对记录进行排序。筛选功能根据查找条件显示记录的子集，而整个 [Recordset](recordset-object-ado.md) 则保留在缓存中。 [Reset](reset-method-rds.md) 方法将执行条件，并用可更新的 **Recordset** 替换当前的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="e307f-p102">The [SortColumn](sortcolumn-property-rds.md), [SortDirection](sortdirection-property-rds.md), [FilterValue](filtervalue-property-rds.md), [FilterCriterion](filtercriterion-property-rds.md), and **FilterColumn** properties provide sorting and filtering functionality on the client-side cache. The sorting functionality orders records by values from one column. The filtering functionality displays a subset of records based on find criteria, while the full [Recordset](recordset-object-ado.md) is maintained in the cache. The [Reset](reset-method-rds.md) method will execute the criteria and replace the current **Recordset** with an updatable **Recordset**.</span></span>

