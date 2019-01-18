---
title: ParameterDirectionEnum
TOCTitle: ParameterDirectionEnum
ms:assetid: 73a97522-010e-d8f4-1a30-15df2469cad4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249473(v=office.15)
ms:contentKeyID: 48545643
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: fac07165416841691ee7bc3ca5dfcdc366861023
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28715499"
---
# <a name="parameterdirectionenum"></a><span data-ttu-id="c7cc8-102">ParameterDirectionEnum</span><span class="sxs-lookup"><span data-stu-id="c7cc8-102">ParameterDirectionEnum</span></span>


<span data-ttu-id="c7cc8-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c7cc8-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c7cc8-104">用于指定 [Parameter 对象 (ADO)](parameter-object-ado.md) 是代表输入参数、输出参数、输入和输出参数两者，还是来自存储过程的返回值。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-104">Specifies whether the [Parameter](parameter-object-ado.md) represents an input parameter, an output parameter, both an input and an output parameter, or the return value from a stored procedure.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c7cc8-105">常量</span><span class="sxs-lookup"><span data-stu-id="c7cc8-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="c7cc8-106">值</span><span class="sxs-lookup"><span data-stu-id="c7cc8-106">Value</span></span></p></th>
<th><p><span data-ttu-id="c7cc8-107">说明</span><span class="sxs-lookup"><span data-stu-id="c7cc8-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7cc8-108"><strong>adParamInput</strong></span><span class="sxs-lookup"><span data-stu-id="c7cc8-108"><strong>adParamInput</strong></span></span></p></td>
<td><p><span data-ttu-id="c7cc8-109">1</span><span class="sxs-lookup"><span data-stu-id="c7cc8-109">1</span></span></p></td>
<td><p><span data-ttu-id="c7cc8-p101">默认值。指示参数代表输入参数。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-p101">Default. Indicates that the parameter represents an input parameter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7cc8-112"><strong>adParamInputOutput</strong></span><span class="sxs-lookup"><span data-stu-id="c7cc8-112"><strong>adParamInputOutput</strong></span></span></p></td>
<td><p><span data-ttu-id="c7cc8-113">3</span><span class="sxs-lookup"><span data-stu-id="c7cc8-113">3</span></span></p></td>
<td><p><span data-ttu-id="c7cc8-114">指示参数代表输入参数和输出参数两者。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-114">Indicates that the parameter represents both an input and output parameter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7cc8-115"><strong>adParamOutput</strong></span><span class="sxs-lookup"><span data-stu-id="c7cc8-115"><strong>adParamOutput</strong></span></span></p></td>
<td><p><span data-ttu-id="c7cc8-116">2</span><span class="sxs-lookup"><span data-stu-id="c7cc8-116">2</span></span></p></td>
<td><p><span data-ttu-id="c7cc8-117">指示参数代表输出参数。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-117">Indicates that the parameter represents an output parameter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7cc8-118"><strong>adParamReturnValue</strong></span><span class="sxs-lookup"><span data-stu-id="c7cc8-118"><strong>adParamReturnValue</strong></span></span></p></td>
<td><p><span data-ttu-id="c7cc8-119">4</span><span class="sxs-lookup"><span data-stu-id="c7cc8-119">4</span></span></p></td>
<td><p><span data-ttu-id="c7cc8-120">指示参数代表返回值。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-120">Indicates that the parameter represents a return value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7cc8-121"><strong>adParamUnknown</strong></span><span class="sxs-lookup"><span data-stu-id="c7cc8-121"><strong>adParamUnknown</strong></span></span></p></td>
<td><p><span data-ttu-id="c7cc8-122">0</span><span class="sxs-lookup"><span data-stu-id="c7cc8-122">0</span></span></p></td>
<td><p><span data-ttu-id="c7cc8-123">指示参数方向未知。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-123">Indicates that the parameter direction is unknown.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="c7cc8-124">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="c7cc8-124">ADO/WFC equivalent</span></span>

<span data-ttu-id="c7cc8-125">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="c7cc8-125">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c7cc8-126">常量</span><span class="sxs-lookup"><span data-stu-id="c7cc8-126">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7cc8-127">AdoEnums.ParameterDirection.INPUT</span><span class="sxs-lookup"><span data-stu-id="c7cc8-127">AdoEnums.ParameterDirection.INPUT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7cc8-128">AdoEnums.ParameterDirection.INPUTOUTPUT</span><span class="sxs-lookup"><span data-stu-id="c7cc8-128">AdoEnums.ParameterDirection.INPUTOUTPUT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7cc8-129">AdoEnums.ParameterDirection.OUTPUT</span><span class="sxs-lookup"><span data-stu-id="c7cc8-129">AdoEnums.ParameterDirection.OUTPUT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7cc8-130">AdoEnums.ParameterDirection.RETURNVALUE</span><span class="sxs-lookup"><span data-stu-id="c7cc8-130">AdoEnums.ParameterDirection.RETURNVALUE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7cc8-131">AdoEnums.ParameterDirection.UNKNOWN</span><span class="sxs-lookup"><span data-stu-id="c7cc8-131">AdoEnums.ParameterDirection.UNKNOWN</span></span></p></td>
</tr>
</tbody>
</table>

