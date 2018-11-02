---
title: Reset 方法 (RDS-访问桌面数据库引用)
TOCTitle: Reset method (RDS)
ms:assetid: 169ebd1e-6071-613e-c065-3af060167456
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248924(v=office.15)
ms:contentKeyID: 48543435
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e336a7ddf4db6e927c185b33a4138ab8dd5d5e9a
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25925966"
---
# <a name="reset-method-rds"></a><span data-ttu-id="e4b48-102">Reset 方法 (RDS)</span><span class="sxs-lookup"><span data-stu-id="e4b48-102">Reset method (RDS)</span></span>


<span data-ttu-id="e4b48-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e4b48-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e4b48-104">根据指定的排序和筛选属性，对客户端 **Recordset** 执行排序或筛选。</span><span class="sxs-lookup"><span data-stu-id="e4b48-104">Executes the sort or filter on a client-side **Recordset** based on the specified sort and filter properties.</span></span>

## <a name="syntax"></a><span data-ttu-id="e4b48-105">语法</span><span class="sxs-lookup"><span data-stu-id="e4b48-105">Syntax</span></span>

<span data-ttu-id="e4b48-106">*DataControl*。重置 （*值*）</span><span class="sxs-lookup"><span data-stu-id="e4b48-106">*DataControl*.Reset(*value*)</span></span>

## <a name="parameters"></a><span data-ttu-id="e4b48-107">参数</span><span class="sxs-lookup"><span data-stu-id="e4b48-107">Parameters</span></span>

  - <span data-ttu-id="e4b48-108">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="e4b48-108">*DataControl*</span></span>

  - <span data-ttu-id="e4b48-109">一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="e4b48-109">An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>

  - <span data-ttu-id="e4b48-110">*value*</span><span class="sxs-lookup"><span data-stu-id="e4b48-110">*value*</span></span>

  - <span data-ttu-id="e4b48-p101">可选。 **Boolean** 值，如果要对当前"已筛选的"行集进行筛选，则此参数为 **True** （默认值）。 **False** 指示对原始行集进行筛选，删除以前的所有筛选选项。</span><span class="sxs-lookup"><span data-stu-id="e4b48-p101">Optional. A **Boolean** value that is **True** (default) if you want to filter on the current "filtered" rowset. **False** indicates that you filter on the original rowset, removing any previous filter options.</span></span>

## <a name="remarks"></a><span data-ttu-id="e4b48-114">备注</span><span class="sxs-lookup"><span data-stu-id="e4b48-114">Remarks</span></span>

<span data-ttu-id="e4b48-p102">[SortColumn](sortcolumn-property-rds.md)、[SortDirection](sortdirection-property-rds.md)、[FilterValue](filtervalue-property-rds.md)、[FilterCriterion](filtercriterion-property-rds.md) 和 [FilterColumn](filtercolumn-property-rds.md) 属性提供了对客户端缓存进行排序和筛选的功能。排序功能将按照一列中的值对记录进行排序。筛选功能基于查找条件显示记录的子集，而缓存中保留有完整的 [Recordset](recordset-object-ado.md)。 **Reset** 方法将执行查找条件，并用可更新的 **Recordset** 替换当前 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="e4b48-p102">The [SortColumn](sortcolumn-property-rds.md), [SortDirection](sortdirection-property-rds.md), [FilterValue](filtervalue-property-rds.md), [FilterCriterion](filtercriterion-property-rds.md), and [FilterColumn](filtercolumn-property-rds.md) properties provide sorting and filtering functionality on the client-side cache. The sorting functionality orders records by values from one column. The filtering functionality displays a subset of records based on a find criteria, while the full [Recordset](recordset-object-ado.md) is maintained in the cache. The **Reset** method will execute the criteria and replace the current **Recordset** with an updatable **Recordset**.</span></span>

<span data-ttu-id="e4b48-p103">如果对原始数据所做的更改尚未提交，则 **Reset** 方法将失败。首先，请使用 [SubmitChanges](submitchanges-method-rds.md) 方法将所有更改保存在读/写 **Recordset** 中，然后使用 **Reset** 方法对记录进行排序或筛选。</span><span class="sxs-lookup"><span data-stu-id="e4b48-p103">If there are changes to the original data that haven't yet been submitted, the **Reset** method will fail. First, use the [SubmitChanges](submitchanges-method-rds.md) method to save any changes in a read/write **Recordset**, and then use the **Reset** method to sort or filter the records.</span></span>

<span data-ttu-id="e4b48-121">如果您想要对您行集执行多个筛选器，则可以使用可选的*布尔型*参数，则用**Reset**方法。</span><span class="sxs-lookup"><span data-stu-id="e4b48-121">If you want to perform more than one filter on your rowset, you can use the optional *Boolean* argument with the **Reset** method.</span></span> <span data-ttu-id="e4b48-122">以下示例显示了具体的操作方法：</span><span class="sxs-lookup"><span data-stu-id="e4b48-122">The following example shows how to do this:</span></span>

