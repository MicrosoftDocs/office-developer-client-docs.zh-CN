---
title: Ordinal 属性（ADO MD 单元格）
TOCTitle: Ordinal Property (ADO MD Cell)
ms:assetid: be705823-6c5e-0c8f-f780-87df19423a72
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249924(v=office.15)
ms:contentKeyID: 48547462
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 284e2cac2c1a86d87e39d9913a262fbafb435ece
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466275"
---
# <a name="ordinal-property-ado-md-cell"></a><span data-ttu-id="20c38-102">Ordinal 属性（ADO MD 单元格）</span><span class="sxs-lookup"><span data-stu-id="20c38-102">Ordinal Property (ADO MD Cell)</span></span>


<span data-ttu-id="20c38-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="20c38-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="20c38-104">根据单元格在单元格集内的位置唯一标识该单元格。</span><span class="sxs-lookup"><span data-stu-id="20c38-104">Uniquely identifies a cell by its position within a cellset.</span></span>

## <a name="return-values"></a><span data-ttu-id="20c38-105">返回值</span><span class="sxs-lookup"><span data-stu-id="20c38-105">Return Values</span></span>

<span data-ttu-id="20c38-106">返回一个 **Long** 整数值，并且该值为只读。</span><span class="sxs-lookup"><span data-stu-id="20c38-106">Returns a **Long** integer and is read-only.</span></span>

## <a name="remarks"></a><span data-ttu-id="20c38-107">说明</span><span class="sxs-lookup"><span data-stu-id="20c38-107">Remarks</span></span>

<span data-ttu-id="20c38-p101">单元格的序号值唯一地标识单元格集中的单元格。从概念上来说，单元格在单元格集中进行了编号，就像单元格集是一个 *p* 维数组那样（此处 *p* 是 [Axes 集合 (ADO MD)](axes-collection-ado-md.md) 数目）。单元格按以行为主的顺序从零开始编号。</span><span class="sxs-lookup"><span data-stu-id="20c38-p101">The cell's ordinal value uniquely identifies the cell within a cellset. Conceptually, cells are numbered in a cellset as if the cellset were a *p*-dimensional array, where *p* is the number of [axes](axes-collection-ado-md.md). Cells are numbered starting from zero in row-major order.</span></span>

<span data-ttu-id="20c38-111">将单元格的序号值与 [Cellset](item-property-ado-md-cellset.md) 对象的 [Item](cellset-object-ado-md.md) 属性一起使用，可以快速检索 [Cell 对象 (ADO MD)](cell-object-ado-md.md)。</span><span class="sxs-lookup"><span data-stu-id="20c38-111">The cell's ordinal value can be used with the [Item](item-property-ado-md-cellset.md) property of the [Cellset](cellset-object-ado-md.md) object to quickly retrieve the [Cell](cell-object-ado-md.md).</span></span>

