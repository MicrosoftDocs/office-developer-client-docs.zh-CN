---
title: SortDirection 属性 (RDS)
TOCTitle: SortDirection property (RDS)
ms:assetid: 33de0dce-f371-6a54-d179-0627939f5b14
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249106(v=office.15)
ms:contentKeyID: 48544119
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: fd09eb22d9f751ab1140db948356d2b168b30afb
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28711355"
---
# <a name="sortdirection-property-rds"></a><span data-ttu-id="44767-102">SortDirection 属性 (RDS)</span><span class="sxs-lookup"><span data-stu-id="44767-102">SortDirection property (RDS)</span></span>

<span data-ttu-id="44767-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="44767-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="44767-104">指示排序顺序是升序还是降序。</span><span class="sxs-lookup"><span data-stu-id="44767-104">Indicates whether a sort order is ascending or descending.</span></span>

## <a name="syntax"></a><span data-ttu-id="44767-105">语法</span><span class="sxs-lookup"><span data-stu-id="44767-105">Syntax</span></span>

<span data-ttu-id="44767-106">*DataControl*。SortDirection =*值*</span><span class="sxs-lookup"><span data-stu-id="44767-106">*DataControl*.SortDirection = *value*</span></span>

## <a name="parameters"></a><span data-ttu-id="44767-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="44767-107">Parameters</span></span>

|<span data-ttu-id="44767-108">参数</span><span class="sxs-lookup"><span data-stu-id="44767-108">Parameter</span></span>|<span data-ttu-id="44767-109">说明</span><span class="sxs-lookup"><span data-stu-id="44767-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="44767-110">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="44767-110">*DataControl*</span></span> |<span data-ttu-id="44767-111">一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="44767-111">An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>|
|<span data-ttu-id="44767-112">*Value*</span><span class="sxs-lookup"><span data-stu-id="44767-112">*Value*</span></span> |<span data-ttu-id="44767-p101">一个 **Boolean** 值，如果设置为 **True** ，则指示升序排序。 **False** 指示降序排序。</span><span class="sxs-lookup"><span data-stu-id="44767-p101">A **Boolean** value that, when set to **True**, indicates the sort direction is ascending. **False** indicates descending order.</span></span>|

## <a name="remarks"></a><span data-ttu-id="44767-115">备注</span><span class="sxs-lookup"><span data-stu-id="44767-115">Remarks</span></span>

<span data-ttu-id="44767-p102">[SortColumn](sortcolumn-property-rds.md)、 **SortDirection** 、 [FilterValue](filtervalue-property-rds.md)、[FilterCriterion](filtercriterion-property-rds.md) 和 [FilterColumn](filtercolumn-property-rds.md) 属性提供客户端缓存的排序和筛选功能。排序功能根据某一列的值对记录进行排序。筛选功能根据查找条件显示记录的子集，而整个 [Recordset](recordset-object-ado.md) 则保留在缓存中。 **Reset** 方法将执行条件，并用可更新的 **Recordset** 替换当前的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="44767-p102">The [SortColumn](sortcolumn-property-rds.md), **SortDirection**, [FilterValue](filtervalue-property-rds.md), [FilterCriterion](filtercriterion-property-rds.md), and [FilterColumn](filtercolumn-property-rds.md) properties provide sorting and filtering functionality on the client-side cache. The sorting functionality orders records by values from one column. The filtering functionality displays a subset of records based on find criteria, while the full [Recordset](recordset-object-ado.md) is maintained in the cache. The **Reset** method will execute the criteria and replace the current **Recordset** with an updatable **Recordset**.</span></span>

