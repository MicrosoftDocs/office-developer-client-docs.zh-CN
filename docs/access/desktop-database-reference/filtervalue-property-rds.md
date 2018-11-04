---
title: FilterValue 属性 (RDS)
TOCTitle: FilterValue property (RDS)
ms:assetid: 66dc14cd-cc14-78cb-cb05-91eefb17ea47
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249399(v=office.15)
ms:contentKeyID: 48545350
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0de54097c7992583851bbbd7b04c40f10fbca76e
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949479"
---
# <a name="filtervalue-property-rds"></a><span data-ttu-id="84e10-102">FilterValue 属性 (RDS)</span><span class="sxs-lookup"><span data-stu-id="84e10-102">FilterValue property (RDS)</span></span>

<span data-ttu-id="84e10-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="84e10-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="84e10-104">指示用于筛选记录的值。</span><span class="sxs-lookup"><span data-stu-id="84e10-104">Indicates the value with which to filter records.</span></span>

## <a name="syntax"></a><span data-ttu-id="84e10-105">语法</span><span class="sxs-lookup"><span data-stu-id="84e10-105">Syntax</span></span>

<span data-ttu-id="84e10-106">*DataControl*。FilterValue =*字符串*</span><span class="sxs-lookup"><span data-stu-id="84e10-106">*DataControl*.FilterValue = *String*</span></span>

## <a name="parameters"></a><span data-ttu-id="84e10-107">参数</span><span class="sxs-lookup"><span data-stu-id="84e10-107">Parameters</span></span>

|<span data-ttu-id="84e10-108">参数</span><span class="sxs-lookup"><span data-stu-id="84e10-108">Parameter</span></span>|<span data-ttu-id="84e10-109">说明</span><span class="sxs-lookup"><span data-stu-id="84e10-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="84e10-110">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="84e10-110">*DataControl*</span></span> |<span data-ttu-id="84e10-111">一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="84e10-111">An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>|
|<span data-ttu-id="84e10-112">*String*</span><span class="sxs-lookup"><span data-stu-id="84e10-112">*String*</span></span> |<span data-ttu-id="84e10-113">一个**字符串**值，该值代表数据值用于筛选记录 （例如，'Programmer' 或 125）。</span><span class="sxs-lookup"><span data-stu-id="84e10-113">A **String** value that represents a data value with which to filter records (for example, 'Programmer' or 125 ).</span></span>|

## <a name="remarks"></a><span data-ttu-id="84e10-114">备注</span><span class="sxs-lookup"><span data-stu-id="84e10-114">Remarks</span></span>

<span data-ttu-id="84e10-115">[SortColumn](sortcolumn-property-rds.md)、[SortDirection](sortdirection-property-rds.md)、**FilterValue**、[FilterCriterion](filtercriterion-property-rds.md) 和 [FilterColumn](filtercolumn-property-rds.md) 属性提供了对客户端缓存进行排序和筛选的功能。</span><span class="sxs-lookup"><span data-stu-id="84e10-115">The [SortColumn](sortcolumn-property-rds.md), [SortDirection](sortdirection-property-rds.md), **FilterValue**, [FilterCriterion](filtercriterion-property-rds.md), and [FilterColumn](filtercolumn-property-rds.md) properties provide sorting and filtering functionality on the client-side cache.</span></span> 

<span data-ttu-id="84e10-116">排序功能根据某一列的值对记录进行排序。</span><span class="sxs-lookup"><span data-stu-id="84e10-116">The sorting functionality orders records by values from one column.</span></span> <span data-ttu-id="84e10-117">筛选功能根据查找条件显示记录的子集，而整个 [Recordset](recordset-object-ado.md) 则保留在缓存中。</span><span class="sxs-lookup"><span data-stu-id="84e10-117">The filtering functionality displays a subset of records based on find criteria, while the full [Recordset](recordset-object-ado.md) is maintained in the cache.</span></span> <span data-ttu-id="84e10-118">[Reset](reset-method-rds.md) 方法将执行条件，并用可更新的 **Recordset** 替换当前的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="84e10-118">The [Reset](reset-method-rds.md) method will execute the criteria and replace the current **Recordset** with an updatable **Recordset**.</span></span>

<span data-ttu-id="84e10-119">空值将导致出现类型不匹配错误。</span><span class="sxs-lookup"><span data-stu-id="84e10-119">Null values result in a type mismatch error.</span></span>

