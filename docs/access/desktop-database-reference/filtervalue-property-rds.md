---
title: FilterValue 属性 (RDS)
TOCTitle: FilterValue property (RDS)
ms:assetid: 66dc14cd-cc14-78cb-cb05-91eefb17ea47
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249399(v=office.15)
ms:contentKeyID: 48545350
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e2573500fe47c69dfd1779ecc4ad5e0abb7dcf8c
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25925301"
---
# <a name="filtervalue-property-rds"></a><span data-ttu-id="0015b-102">FilterValue 属性 (RDS)</span><span class="sxs-lookup"><span data-stu-id="0015b-102">FilterValue property (RDS)</span></span>


<span data-ttu-id="0015b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="0015b-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="0015b-104">指示用于筛选记录的值。</span><span class="sxs-lookup"><span data-stu-id="0015b-104">Indicates the value with which to filter records.</span></span>

## <a name="syntax"></a><span data-ttu-id="0015b-105">语法</span><span class="sxs-lookup"><span data-stu-id="0015b-105">Syntax</span></span>

<span data-ttu-id="0015b-106">*DataControl*。FilterValue =*字符串*</span><span class="sxs-lookup"><span data-stu-id="0015b-106">*DataControl*.FilterValue = *String*</span></span>

## <a name="parameters"></a><span data-ttu-id="0015b-107">参数</span><span class="sxs-lookup"><span data-stu-id="0015b-107">Parameters</span></span>

  - <span data-ttu-id="0015b-108">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="0015b-108">*DataControl*</span></span>

  - <span data-ttu-id="0015b-109">一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="0015b-109">An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>

  - <span data-ttu-id="0015b-110">*String*</span><span class="sxs-lookup"><span data-stu-id="0015b-110">*String*</span></span>

  - <span data-ttu-id="0015b-111">一个**字符串**值，该值代表数据值用于筛选记录 （例如，'Programmer' 或 125）。</span><span class="sxs-lookup"><span data-stu-id="0015b-111">A **String** value that represents a data value with which to filter records (for example, 'Programmer' or 125 ).</span></span>

## <a name="remarks"></a><span data-ttu-id="0015b-112">备注</span><span class="sxs-lookup"><span data-stu-id="0015b-112">Remarks</span></span>

<span data-ttu-id="0015b-p101">[SortColumn](sortcolumn-property-rds.md)、[SortDirection](sortdirection-property-rds.md)、 **FilterValue** 、 [FilterCriterion](filtercriterion-property-rds.md) 和 [FilterColumn](filtercolumn-property-rds.md) 属性提供客户端缓存的排序和筛选功能。排序功能根据某一列的值对记录进行排序。筛选功能根据查找条件显示记录的子集，而整个 [Recordset](recordset-object-ado.md) 则保留在缓存中。 [Reset](reset-method-rds.md) 方法将执行条件，并用可更新的 **Recordset** 替换当前的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="0015b-p101">The [SortColumn](sortcolumn-property-rds.md), [SortDirection](sortdirection-property-rds.md), **FilterValue**, [FilterCriterion](filtercriterion-property-rds.md), and [FilterColumn](filtercolumn-property-rds.md) properties provide sorting and filtering functionality on the client-side cache. The sorting functionality orders records by values from one column. The filtering functionality displays a subset of records based on find criteria, while the full [Recordset](recordset-object-ado.md) is maintained in the cache. The [Reset](reset-method-rds.md) method will execute the criteria and replace the current **Recordset** with an updatable **Recordset**.</span></span>

<span data-ttu-id="0015b-117">空值将导致出现类型不匹配错误。</span><span class="sxs-lookup"><span data-stu-id="0015b-117">Null values result in a type mismatch error.</span></span>

