---
title: Item 属性（ADO MD 单元格集）
TOCTitle: Item property (ADO MD Cellset)
ms:assetid: 47510643-47af-0bfd-dc1f-ab984057bcd3
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249220(v=office.15)
ms:contentKeyID: 48544595
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 99f381ad2f38dc7d2c467ed1e40e4084032006d1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290865"
---
# <a name="item-property-ado-md-cellset"></a><span data-ttu-id="10167-102">Item 属性（ADO MD 单元格集）</span><span class="sxs-lookup"><span data-stu-id="10167-102">Item property (ADO MD Cellset)</span></span>

<span data-ttu-id="10167-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="10167-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="10167-104">使用单元格的坐标从单元格集中检索单元格。</span><span class="sxs-lookup"><span data-stu-id="10167-104">Retrieves a cell from a cellset using its coordinates.</span></span>

## <a name="syntax"></a><span data-ttu-id="10167-105">语法</span><span class="sxs-lookup"><span data-stu-id="10167-105">Syntax</span></span>

<span data-ttu-id="10167-106">设置*单元格* = *集*。Item (*职位*)</span><span class="sxs-lookup"><span data-stu-id="10167-106">Set*Cell* = *Cellset*.Item (*Positions*)</span></span>

## <a name="parameters"></a><span data-ttu-id="10167-107">参数</span><span class="sxs-lookup"><span data-stu-id="10167-107">Parameters</span></span>

|<span data-ttu-id="10167-108">参数</span><span class="sxs-lookup"><span data-stu-id="10167-108">Parameter</span></span>|<span data-ttu-id="10167-109">描述</span><span class="sxs-lookup"><span data-stu-id="10167-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="10167-110">*Positions*</span><span class="sxs-lookup"><span data-stu-id="10167-110">*Positions*</span></span> |<span data-ttu-id="10167-111">唯一指定单元格的值的**Variant 数组**。</span><span class="sxs-lookup"><span data-stu-id="10167-111">A **Variant array** of values that uniquely specify a cell.</span></span> <span data-ttu-id="10167-112">*Positions* 可以为下列值之一：</span><span class="sxs-lookup"><span data-stu-id="10167-112">*Positions* can be one of the following:</span></span><br/><br/><span data-ttu-id="10167-113">-位置号的数组</span><span class="sxs-lookup"><span data-stu-id="10167-113">- An array of position numbers</span></span><br/><span data-ttu-id="10167-114">-成员名称的数组</span><span class="sxs-lookup"><span data-stu-id="10167-114">- An array of member names</span></span><br/><span data-ttu-id="10167-115">-序号位置</span><span class="sxs-lookup"><span data-stu-id="10167-115">- The ordinal position</span></span> |

## <a name="remarks"></a><span data-ttu-id="10167-116">注解</span><span class="sxs-lookup"><span data-stu-id="10167-116">Remarks</span></span>

<span data-ttu-id="10167-p102">使用 **Item** 属性可以返回 [Cellset](cellset-object-ado-md.md) 对象中的 [Cell](cell-object-ado-md.md) 对象。如果 **Item** 属性找不到对应于 *Positions* 参数的单元格，将发生错误。</span><span class="sxs-lookup"><span data-stu-id="10167-p102">Use the **Item** property to return a [Cell](cell-object-ado-md.md) object within a [Cellset](cellset-object-ado-md.md) object. If the **Item** property cannot find the cell corresponding to the *Positions* argument, an error occurs.</span></span>

<span data-ttu-id="10167-119">**Item** 属性是 **Cellset** 对象的默认属性。</span><span class="sxs-lookup"><span data-stu-id="10167-119">The **Item** property is the default property for the **Cellset** object.</span></span> <span data-ttu-id="10167-120">以下语法格式可互换：</span><span class="sxs-lookup"><span data-stu-id="10167-120">The following syntax forms are interchangeable:</span></span>

```vb
    Cellset.Item ( Positions )
    Cellset ( Positions )
```

<span data-ttu-id="10167-p104">*Positions* 参数指定要返回的单元格。您可以按序号位置或沿每条轴的位置指定单元格。按沿每条轴的位置指定单元格时，可以指定位置的数值，或者每个位置的成员的名称。</span><span class="sxs-lookup"><span data-stu-id="10167-p104">The *Positions* argument specifies which cell to return. You can specify the cell by ordinal position or by the position along each axis. When specifying the cell by position along each axis, you can specify the numeric value of the position or the names of the members for each position.</span></span>

<span data-ttu-id="10167-p105">序号位置是唯一标识**单元格集**中每个单元格的数字。从概念上来说，单元格在**单元格集**中进行了编号，就像**单元格集**是一个 *p* 维数组那样（此处 *p* 是轴数目）。单元格按以行为主的顺序进行编号。</span><span class="sxs-lookup"><span data-stu-id="10167-p105">The ordinal position is a number that uniquely identifies one cell within the **Cellset**. Conceptually, cells are numbered in a **Cellset** as if the **Cellset** were a *p*-dimensional array, where *p* is the number of axes. Cells are addressed in row-major order.</span></span>

<span data-ttu-id="10167-p106">如果将成员名称作为字符串传递给 **Item** ，则必须以数值轴标识符的升序列出成员。在一条轴中，成员必须以维嵌套的升序列出，也就是说，最外侧的维的成员最先列出，然后跟随内侧的维的成员。每个维应由单独的字符串表示，且成员字符串列表应由逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="10167-p106">If member names are passed as strings to **Item**, the members must be listed in increasing order of the numeric axis identifiers. Within an axis, the members must be listed in increasing order of dimension nesting — that is, the outermost dimension's member comes first, followed by members of inner dimensions. Each dimension should be represented by a separate string, and the list of member strings should be separated by commas.</span></span>


> [!NOTE]
> <span data-ttu-id="10167-p107">[!注释] 您的数据提供程序可能不支持按成员名称检索单元格。有关详细信息，请参阅您的提供程序文档。</span><span class="sxs-lookup"><span data-stu-id="10167-p107">Retrieving cells by member name may not be supported by your data provider. See the documentation for your provider for more information.</span></span>


