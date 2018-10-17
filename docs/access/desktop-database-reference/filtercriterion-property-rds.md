---
title: FilterCriterion 属性 (RDS)
TOCTitle: FilterCriterion Property (RDS)
ms:assetid: 51e6cb64-a404-114e-8e1a-0744cceeec3e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249267(v=office.15)
ms:contentKeyID: 48544834
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3b847318c5fe0132fbc53f588b4478b7f37ec4ba
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468836"
---
# <a name="filtercriterion-property-rds"></a><span data-ttu-id="7b5c7-102">FilterCriterion 属性 (RDS)</span><span class="sxs-lookup"><span data-stu-id="7b5c7-102">FilterCriterion Property (RDS)</span></span>


<span data-ttu-id="7b5c7-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="7b5c7-103">**Applies to**: Access 2013 | Office 2013</span></span>



<span data-ttu-id="7b5c7-104">指示筛选值中使用的求值运算符。</span><span class="sxs-lookup"><span data-stu-id="7b5c7-104">Indicates the evaluation operator to use in the filter value.</span></span>

## <a name="syntax"></a><span data-ttu-id="7b5c7-105">语法</span><span class="sxs-lookup"><span data-stu-id="7b5c7-105">Syntax</span></span>

<span data-ttu-id="7b5c7-106">*DataControl*。FilterCriterion =*字符串*</span><span class="sxs-lookup"><span data-stu-id="7b5c7-106">*DataControl*.FilterCriterion = *String*</span></span>

## <a name="parameters"></a><span data-ttu-id="7b5c7-107">参数</span><span class="sxs-lookup"><span data-stu-id="7b5c7-107">Parameters</span></span>

  - <span data-ttu-id="7b5c7-108">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="7b5c7-108">*DataControl*</span></span>

  - <span data-ttu-id="7b5c7-109">一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="7b5c7-109">An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>

  - <span data-ttu-id="7b5c7-110">*String*</span><span class="sxs-lookup"><span data-stu-id="7b5c7-110">*String*</span></span>

  - <span data-ttu-id="7b5c7-111">一个 **String** 值，指定记录的 [FilterValue](filtervalue-property-rds.md) 的求值运算符。</span><span class="sxs-lookup"><span data-stu-id="7b5c7-111">A **String** value that specifies the evaluation operator of the [FilterValue](filtervalue-property-rds.md) to the records.</span></span> <span data-ttu-id="7b5c7-112">可以是以下任一： \<， \<= \>， \>=、 = 或\< \>。</span><span class="sxs-lookup"><span data-stu-id="7b5c7-112">Can be any one of the following: \<, \<=, \>, \>=, =, or \<\>.</span></span>

## <a name="remarks"></a><span data-ttu-id="7b5c7-113">备注</span><span class="sxs-lookup"><span data-stu-id="7b5c7-113">Remarks</span></span>

<span data-ttu-id="7b5c7-p102">[SortColumn](sortcolumn-property-rds.md)、 [SortDirection](sortdirection-property-rds.md) 、 [FilterValue](filtervalue-property-rds.md)、**FilterCriterion** 和 [FilterColumn](filtercolumn-property-rds.md) 属性提供客户端缓存的排序和筛选功能。排序功能根据某一列的值对记录进行排序。筛选功能根据查找条件显示记录的子集，而整个 [Recordset](recordset-object-ado.md) 则保留在缓存中。 [Reset](reset-method-rds.md) 方法将执行条件，并用可更新的 **Recordset** 替换当前的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="7b5c7-p102">The [SortColumn](sortcolumn-property-rds.md), [SortDirection](sortdirection-property-rds.md), [FilterValue](filtervalue-property-rds.md), **FilterCriterion**, and [FilterColumn](filtercolumn-property-rds.md) properties provide sorting and filtering functionality on the client-side cache. The sorting functionality orders records by values from one column. The filtering functionality displays a subset of records based on find criteria, while the full [Recordset](recordset-object-ado.md) is maintained in the cache. The [Reset](reset-method-rds.md) method will execute the criteria and replace the current **Recordset** with an updatable **Recordset**.</span></span>

<span data-ttu-id="7b5c7-118">"\!="运算符对**FilterCriterion**; 无效请改用"\<\>"。</span><span class="sxs-lookup"><span data-stu-id="7b5c7-118">The "\!=" operator is not valid for **FilterCriterion**; instead, use "\<\>".</span></span>

<span data-ttu-id="7b5c7-p103">如果同时设置了筛选和排序属性并调用 **Reset** 方法，将首先筛选行集，然后再对其进行排序。对于升序排列，Null 值位于顶部；对于降序排列，Null 值位于底部（默认行为是升序）。</span><span class="sxs-lookup"><span data-stu-id="7b5c7-p103">If both the filter and sort properties are set and you call the **Reset** method, the rowset is first filtered and then it is sorted. For ascending sorts, the null values are at the top; for descending sorts, null values are at the bottom (ascending is default behavior).</span></span>
