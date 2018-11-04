---
title: Item 属性（ADO MD 单元格）
TOCTitle: Item property (ADO MD Cellset)
ms:assetid: 47510643-47af-0bfd-dc1f-ab984057bcd3
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249220(v=office.15)
ms:contentKeyID: 48544595
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: fdf405ab5cd59e7ab4268e2fea870272836fb164
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949605"
---
# <a name="item-property-ado-md-cellset"></a><span data-ttu-id="15904-102">Item 属性（ADO MD 单元格）</span><span class="sxs-lookup"><span data-stu-id="15904-102">Item property (ADO MD Cellset)</span></span>

<span data-ttu-id="15904-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="15904-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="15904-104">使用单元格的坐标从单元格集中检索单元格。</span><span class="sxs-lookup"><span data-stu-id="15904-104">Retrieves a cell from a cellset using its coordinates.</span></span>

## <a name="syntax"></a><span data-ttu-id="15904-105">语法</span><span class="sxs-lookup"><span data-stu-id="15904-105">Syntax</span></span>

<span data-ttu-id="15904-106">设置*单元格* = *单元格集*。项目 (*位置*)</span><span class="sxs-lookup"><span data-stu-id="15904-106">Set*Cell* = *Cellset*.Item (*Positions*)</span></span>

## <a name="parameters"></a><span data-ttu-id="15904-107">参数</span><span class="sxs-lookup"><span data-stu-id="15904-107">Parameters</span></span>

|<span data-ttu-id="15904-108">参数</span><span class="sxs-lookup"><span data-stu-id="15904-108">Parameter</span></span>|<span data-ttu-id="15904-109">说明</span><span class="sxs-lookup"><span data-stu-id="15904-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="15904-110">*Positions*</span><span class="sxs-lookup"><span data-stu-id="15904-110">*Positions*</span></span> |<span data-ttu-id="15904-111">唯一指定单元格的值的**Variant 数组**。</span><span class="sxs-lookup"><span data-stu-id="15904-111">A **Variant array** of values that uniquely specify a cell.</span></span> <span data-ttu-id="15904-112">*位置*可以是下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="15904-112">*Positions* can be one of the following:</span></span><br/><br/><span data-ttu-id="15904-113">-一个数组位置编号</span><span class="sxs-lookup"><span data-stu-id="15904-113">- An array of position numbers</span></span><br/><span data-ttu-id="15904-114">-成员名称数组</span><span class="sxs-lookup"><span data-stu-id="15904-114">- An array of member names</span></span><br/><span data-ttu-id="15904-115">-序号位置</span><span class="sxs-lookup"><span data-stu-id="15904-115">- The ordinal position</span></span> |

## <a name="remarks"></a><span data-ttu-id="15904-116">说明</span><span class="sxs-lookup"><span data-stu-id="15904-116">Remarks</span></span>

<span data-ttu-id="15904-117">使用 **Item** 属性可以返回 [Cellset](cell-object-ado-md.md) 对象中的 [Cell](cellset-object-ado-md.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="15904-117">Use the **Item** property to return a [Cell](cell-object-ado-md.md) object within a [Cellset](cellset-object-ado-md.md) object.</span></span> <span data-ttu-id="15904-118">如果**Item**属性找不到单元格对应于*Positions*参数，将发生错误。</span><span class="sxs-lookup"><span data-stu-id="15904-118">If the **Item** property cannot find the cell corresponding to the *Positions* argument, an error occurs.</span></span>

<span data-ttu-id="15904-p103">**Item** 属性是 **Cellset** 对象的默认属性。以下语法格式可互换：</span><span class="sxs-lookup"><span data-stu-id="15904-p103">The **Item** property is the default property for the **Cellset** object. The following syntax forms are interchangeable:</span></span>

```vb
    Cellset.Item ( Positions )
    Cellset ( Positions )
```

<span data-ttu-id="15904-121">*位置*参数指定要返回的单元格。</span><span class="sxs-lookup"><span data-stu-id="15904-121">The *Positions* argument specifies which cell to return.</span></span> <span data-ttu-id="15904-122">您可以按序号位置或沿每条轴的位置指定单元格。</span><span class="sxs-lookup"><span data-stu-id="15904-122">You can specify the cell by ordinal position or by the position along each axis.</span></span> <span data-ttu-id="15904-123">按沿每条轴的位置指定单元格时，可以指定位置的数值，或者每个位置的成员的名称。</span><span class="sxs-lookup"><span data-stu-id="15904-123">When specifying the cell by position along each axis, you can specify the numeric value of the position or the names of the members for each position.</span></span>

<span data-ttu-id="15904-p105">序号位置是唯一标识**单元格集**中每个单元格的数字。从概念上来说，单元格在**单元格集**中进行了编号，就像**单元格集**是一个 *p* 维数组那样（此处 *p* 是轴数目）。单元格按以行为主的顺序进行编号。</span><span class="sxs-lookup"><span data-stu-id="15904-p105">The ordinal position is a number that uniquely identifies one cell within the **Cellset**. Conceptually, cells are numbered in a **Cellset** as if the **Cellset** were a *p*-dimensional array, where *p* is the number of axes. Cells are addressed in row-major order.</span></span>

<span data-ttu-id="15904-p106">如果将成员名称作为字符串传递给 **Item** ，则必须以数值轴标识符的升序列出成员。在一条轴中，成员必须以维嵌套的升序列出，也就是说，最外侧的维的成员最先列出，然后跟随内侧的维的成员。每个维应由单独的字符串表示，且成员字符串列表应由逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="15904-p106">If member names are passed as strings to **Item**, the members must be listed in increasing order of the numeric axis identifiers. Within an axis, the members must be listed in increasing order of dimension nesting — that is, the outermost dimension's member comes first, followed by members of inner dimensions. Each dimension should be represented by a separate string, and the list of member strings should be separated by commas.</span></span>


> [!NOTE]
> <span data-ttu-id="15904-p107">[!注释] 您的数据提供程序可能不支持按成员名称检索单元格。有关详细信息，请参阅您的提供程序文档。</span><span class="sxs-lookup"><span data-stu-id="15904-p107">Retrieving cells by member name may not be supported by your data provider. See the documentation for your provider for more information.</span></span>


