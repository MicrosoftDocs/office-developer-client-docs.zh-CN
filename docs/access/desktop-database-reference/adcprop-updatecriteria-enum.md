---
title: ADCPROP_UPDATECRITERIA_ENUM
TOCTitle: ADCPROP_UPDATECRITERIA_ENUM
ms:assetid: 70da63fa-fa75-9bb4-683d-0fcb4c4a2934
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249450(v=office.15)
ms:contentKeyID: 48545571
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8be93b0b7e4b32e3c040e871ff7d97a95f1e247e
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28704306"
---
# <a name="adcpropupdatecriteriaenum"></a><span data-ttu-id="f69dd-102">ADCPROP\_UPDATECRITERIA\_枚举</span><span class="sxs-lookup"><span data-stu-id="f69dd-102">ADCPROP\_UPDATECRITERIA\_ENUM</span></span>

<span data-ttu-id="f69dd-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="f69dd-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f69dd-104">指定在使用 [Recordset](recordset-object-ado.md) 对象来对数据源中的行进行开放式更新期间可以用哪些字段来检测冲突。</span><span class="sxs-lookup"><span data-stu-id="f69dd-104">Specifies which fields can be used to detect conflicts during an optimistic update of a row of the data source with a [Recordset](recordset-object-ado.md) object.</span></span>

<span data-ttu-id="f69dd-105">这些常量用于 **Recordset** 的“**Update Criteria**”动态属性，该动态属性在 [ADO 动态属性索引](ado-dynamic-property-index.md)中被引用，并在 [Microsoft Cursor Service for OLE DB](microsoft-cursor-service-for-ole-db-ado-service-component.md) 文档中进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="f69dd-105">Use these constants with the **Recordset** "**Update Criteria**" dynamic property, which is referenced in the [ADO Dynamic Property Index](ado-dynamic-property-index.md) and documented in the [Microsoft Cursor Service for OLE DB](microsoft-cursor-service-for-ole-db-ado-service-component.md) documentation.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f69dd-106">常量</span><span class="sxs-lookup"><span data-stu-id="f69dd-106">Constant</span></span></p></th>
<th><p><span data-ttu-id="f69dd-107">值</span><span class="sxs-lookup"><span data-stu-id="f69dd-107">Value</span></span></p></th>
<th><p><span data-ttu-id="f69dd-108">说明</span><span class="sxs-lookup"><span data-stu-id="f69dd-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f69dd-109"><strong>adCriteriaAllCols</strong></span><span class="sxs-lookup"><span data-stu-id="f69dd-109"><strong>adCriteriaAllCols</strong></span></span></p></td>
<td><p><span data-ttu-id="f69dd-110">1</span><span class="sxs-lookup"><span data-stu-id="f69dd-110">1</span></span></p></td>
<td><p><span data-ttu-id="f69dd-111">如果数据源行中的任何列已发生更改，则检测冲突。</span><span class="sxs-lookup"><span data-stu-id="f69dd-111">Detects conflicts if any column of the data source row has been changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f69dd-112"><strong>adCriteriaKey</strong></span><span class="sxs-lookup"><span data-stu-id="f69dd-112"><strong>adCriteriaKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f69dd-113">0</span><span class="sxs-lookup"><span data-stu-id="f69dd-113">0</span></span></p></td>
<td><p><span data-ttu-id="f69dd-114">如果数据源行中的键列已发生更改（这意味着该行已被删除），则检测冲突。</span><span class="sxs-lookup"><span data-stu-id="f69dd-114">Detects conflicts if the key column of the data source row has been changed, which means that the row has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f69dd-115"><strong>adCriteriaTimeStamp</strong></span><span class="sxs-lookup"><span data-stu-id="f69dd-115"><strong>adCriteriaTimeStamp</strong></span></span></p></td>
<td><p><span data-ttu-id="f69dd-116">3</span><span class="sxs-lookup"><span data-stu-id="f69dd-116">3</span></span></p></td>
<td><p><span data-ttu-id="f69dd-117">如果数据源行中的时间戳已发生更改（这意味着在获取 <strong>Recordset</strong> 之后，该行已被访问过），则检测冲突。</span><span class="sxs-lookup"><span data-stu-id="f69dd-117">Detects conflicts if the timestamp of the data source row has been changed, which means the row has been accessed after the <strong>Recordset</strong> was obtained.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f69dd-118"><strong>adCriteriaUpdCols</strong></span><span class="sxs-lookup"><span data-stu-id="f69dd-118"><strong>adCriteriaUpdCols</strong></span></span></p></td>
<td><p><span data-ttu-id="f69dd-119">2</span><span class="sxs-lookup"><span data-stu-id="f69dd-119">2</span></span></p></td>
<td><p><span data-ttu-id="f69dd-120">如果数据源行中与 <strong>Recordset</strong> 的更新字段相对应的任何列已发生更改，则检测冲突。</span><span class="sxs-lookup"><span data-stu-id="f69dd-120">Detects conflicts if any of the columns of the data source row that correspond to updated fields of the <strong>Recordset</strong> have been changed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="f69dd-121">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="f69dd-121">ADO/WFC equivalent</span></span>

<span data-ttu-id="f69dd-122">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="f69dd-122">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f69dd-123">常量</span><span class="sxs-lookup"><span data-stu-id="f69dd-123">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f69dd-124">AdoEnums.AdcPropUpdateCriteria.ALLCOLS</span><span class="sxs-lookup"><span data-stu-id="f69dd-124">AdoEnums.AdcPropUpdateCriteria.ALLCOLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f69dd-125">AdoEnums.AdcPropUpdateCriteria.KEY</span><span class="sxs-lookup"><span data-stu-id="f69dd-125">AdoEnums.AdcPropUpdateCriteria.KEY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f69dd-126">AdoEnums.AdcPropUpdateCriteria.TIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="f69dd-126">AdoEnums.AdcPropUpdateCriteria.TIMESTAMP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f69dd-127">AdoEnums.AdcPropUpdateCriteria.UPDCOLS</span><span class="sxs-lookup"><span data-stu-id="f69dd-127">AdoEnums.AdcPropUpdateCriteria.UPDCOLS</span></span></p></td>
</tr>
</tbody>
</table>

