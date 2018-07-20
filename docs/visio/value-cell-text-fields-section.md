---
title: Value 单元格（“Text Fields”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1095
localization_priority: Normal
ms.assetid: 3ca662c8-1ce4-89a9-3264-1ba533fcd444
description: 包含域的函数。
ms.openlocfilehash: 9bce4cbb1b3955f749cefa18130c6b01fe61244e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781618"
---
# <a name="value-cell-text-fields-section"></a><span data-ttu-id="4844c-103">Value 单元格（“Text Fields”内容）</span><span class="sxs-lookup"><span data-stu-id="4844c-103">Value Cell (Text Fields Section)</span></span>

<span data-ttu-id="4844c-104">包含域的函数。</span><span class="sxs-lookup"><span data-stu-id="4844c-104">Contains the function for a field.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4844c-105">注解</span><span class="sxs-lookup"><span data-stu-id="4844c-105">Remarks</span></span>

<span data-ttu-id="4844c-106">您可以设置此单元格，使用**字段**对话框中的值 （在**插入**选项卡中的**文本**组中，单击**域**）。</span><span class="sxs-lookup"><span data-stu-id="4844c-106">You can set the value of this cell using the **Field** dialog box (on the **Insert** tab, in the **Text** group, click **Field**).</span></span>
  
<span data-ttu-id="4844c-107">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 Value 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="4844c-107">To get a reference to the Value cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4844c-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4844c-108">Cell name:</span></span>  <br/> |<span data-ttu-id="4844c-109">Fields.Value [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="4844c-109">Fields.Value[ *i*  ] where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="4844c-110">若要从某个程序按索引获取对 Value 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="4844c-110">To get a reference to the Value cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4844c-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4844c-111">Section index:</span></span>  <br/> |<span data-ttu-id="4844c-112">**visSectionTextField**</span><span class="sxs-lookup"><span data-stu-id="4844c-112">**visSectionTextField**</span></span> <br/> |
|<span data-ttu-id="4844c-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="4844c-113">Row index:</span></span>  <br/> |<span data-ttu-id="4844c-114">**visRowField** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="4844c-114">**visRowField** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="4844c-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4844c-115">Cell index:</span></span>  <br/> |<span data-ttu-id="4844c-116">**visFieldCell**</span><span class="sxs-lookup"><span data-stu-id="4844c-116">**visFieldCell**</span></span> <br/> |
   
