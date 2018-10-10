---
title: SortColumn 属性 (RDS)
TOCTitle: SortColumn Property (RDS)
ms:assetid: 0a5d157c-9261-960d-6f89-33d9c94b3940
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248835(v=office.15)
ms:contentKeyID: 48543151
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 85f2b031ac105bf900548e90eda6c0feb4b78f96
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467781"
---
# <a name="sortcolumn-property-rds"></a><span data-ttu-id="195ed-102">SortColumn 属性 (RDS)</span><span class="sxs-lookup"><span data-stu-id="195ed-102">SortColumn Property (RDS)</span></span>


<span data-ttu-id="195ed-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="195ed-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="195ed-104">指示作为记录的排序依据的列。</span><span class="sxs-lookup"><span data-stu-id="195ed-104">Indicates by which column to sort the records.</span></span>

## <a name="syntax"></a><span data-ttu-id="195ed-105">语法</span><span class="sxs-lookup"><span data-stu-id="195ed-105">Syntax</span></span>

<span data-ttu-id="195ed-106">*DataControl*。SortColumn =*字符串*</span><span class="sxs-lookup"><span data-stu-id="195ed-106">*DataControl*.SortColumn = *String*</span></span>

## <a name="parameters"></a><span data-ttu-id="195ed-107">参数</span><span class="sxs-lookup"><span data-stu-id="195ed-107">Parameters</span></span>

  - <span data-ttu-id="195ed-108">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="195ed-108">*DataControl*</span></span>

  - <span data-ttu-id="195ed-109">一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="195ed-109">An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>

  - <span data-ttu-id="195ed-110">*String*</span><span class="sxs-lookup"><span data-stu-id="195ed-110">*String*</span></span>

  - <span data-ttu-id="195ed-111">一个 **String** 值，表示作为记录的排序依据的列的名称或别名。</span><span class="sxs-lookup"><span data-stu-id="195ed-111">A **String** value that represents the name or alias of the column by which to sort the records.</span></span>

## <a name="remarks"></a><span data-ttu-id="195ed-112">备注</span><span class="sxs-lookup"><span data-stu-id="195ed-112">Remarks</span></span>

<span data-ttu-id="195ed-p101">**SortColumn**、 [SortDirection](sortdirection-property-rds.md) 、 [FilterValue](filtervalue-property-rds.md)、[FilterCriterion](filtercriterion-property-rds.md) 和 [FilterColumn](filtercolumn-property-rds.md) 属性提供客户端缓存的排序和筛选功能。排序功能根据某一列的值对记录进行排序。筛选功能根据查找条件显示记录的子集，而整个 [Recordset](recordset-object-ado.md) 则保留在缓存中。 [Reset](reset-method-rds.md) 方法将执行条件，并用可更新的 **Recordset** 替换当前的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="195ed-p101">The **SortColumn**, [SortDirection](sortdirection-property-rds.md), [FilterValue](filtervalue-property-rds.md), [FilterCriterion](filtercriterion-property-rds.md), and [FilterColumn](filtercolumn-property-rds.md) properties provide sorting and filtering functionality on the client-side cache. The sorting functionality orders records by values from one column. The filtering functionality displays a subset of records based on find criteria, while the full [Recordset](recordset-object-ado.md) is maintained in the cache. The [Reset](reset-method-rds.md) method will execute the criteria and replace the current **Recordset** with an updatable **Recordset**.</span></span>

<span data-ttu-id="195ed-117">若要对 **Recordset** 进行排序，必须首先保存所有挂起的更改。</span><span class="sxs-lookup"><span data-stu-id="195ed-117">To sort on a **Recordset**, you must first save any pending changes.</span></span> <span data-ttu-id="195ed-118">如果正在使用 **RDS.DataControl** ，则可以使用 [SubmitChanges](submitchanges-method-rds.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="195ed-118">If you are using the **RDS.DataControl**, you can use the [SubmitChanges](submitchanges-method-rds.md) method.</span></span> <span data-ttu-id="195ed-119">例如，如果您**rds.DataControl**是名为 ADC1，您的代码应为 ADC1。SubmitChanges。</span><span class="sxs-lookup"><span data-stu-id="195ed-119">For example, if your **RDS.DataControl** is named ADC1, your code would be ADC1.SubmitChanges .</span></span> <span data-ttu-id="195ed-120">如果正在使用 ADO **Recordset** ，则可以使用其 [UpdateBatch](updatebatch-method-ado.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="195ed-120">If you are using an ADO **Recordset**, you can use its [UpdateBatch](updatebatch-method-ado.md) method.</span></span> <span data-ttu-id="195ed-121">对于用 **CreateRecordset** 方法创建的 **Recordset** 对象，建议使用 [UpdateBatch](createrecordset-method-rds.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="195ed-121">Using **UpdateBatch** is the recommended method for **Recordset** objects created with the [CreateRecordset](createrecordset-method-rds.md) method.</span></span> <span data-ttu-id="195ed-122">例如，您的代码可以 myRS.UpdateBatch 或。</span><span class="sxs-lookup"><span data-stu-id="195ed-122">For example, your code could be myRS.UpdateBatch or .</span></span> <span data-ttu-id="195ed-123">如果正在使用 ADO **Recordset** ，则可以使用其 [UpdateBatch](updatebatch-method-ado.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="195ed-123">If you are using an ADO **Recordset**, you can use its [UpdateBatch](updatebatch-method-ado.md) method.</span></span> <span data-ttu-id="195ed-124">对于用 **CreateRecordset** 方法创建的 **Recordset** 对象，建议使用 [UpdateBatch](createrecordset-method-rds.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="195ed-124">Using **UpdateBatch** is the recommended method for **Recordset** objects created with the [CreateRecordset](createrecordset-method-rds.md) method.</span></span> <span data-ttu-id="195ed-125">例如，您的代码可以是 myRS.UpdateBatch 或 ADC1。Recordset.UpdateBatch。</span><span class="sxs-lookup"><span data-stu-id="195ed-125">For example, your code could be myRS.UpdateBatch or ADC1.Recordset.UpdateBatch .</span></span>

