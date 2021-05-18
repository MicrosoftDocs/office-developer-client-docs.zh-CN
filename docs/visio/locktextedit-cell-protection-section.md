---
title: LockTextEdit 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm665
localization_priority: Normal
ms.assetid: d8de5fa4-826b-e869-4d9f-997361d05fd8
description: 锁定形状的文本，使它无法编辑。
ms.openlocfilehash: f6e5176e3ab654b76c0641b8f642abcf6b1050dd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404496"
---
# <a name="locktextedit-cell-protection-section"></a><span data-ttu-id="9db08-103">LockTextEdit 单元格（“Protection”内容）</span><span class="sxs-lookup"><span data-stu-id="9db08-103">LockTextEdit Cell (Protection Section)</span></span>

<span data-ttu-id="9db08-104">锁定形状的文本，使它无法编辑。</span><span class="sxs-lookup"><span data-stu-id="9db08-104">Locks the text of a shape so that it cannot be edited.</span></span>
  
|<span data-ttu-id="9db08-105">**值**</span><span class="sxs-lookup"><span data-stu-id="9db08-105">**Value**</span></span>|<span data-ttu-id="9db08-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="9db08-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9db08-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="9db08-107">TRUE</span></span>  <br/> |<span data-ttu-id="9db08-108">不能编辑文本。</span><span class="sxs-lookup"><span data-stu-id="9db08-108">Text cannot be edited.</span></span>  <br/> |
| <span data-ttu-id="9db08-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="9db08-109">FALSE</span></span>  <br/> | <span data-ttu-id="9db08-110">能够编辑文本。</span><span class="sxs-lookup"><span data-stu-id="9db08-110">Text can be edited.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9db08-111">备注</span><span class="sxs-lookup"><span data-stu-id="9db08-111">Remarks</span></span>

<span data-ttu-id="9db08-112">您仍然可以通过应用 **“文本”** 对话框（在 **“开始”** 选项卡上，单击 **“字体”** 箭头）中的样式来设置文本的格式。</span><span class="sxs-lookup"><span data-stu-id="9db08-112">You can still format text by applying a style in the **Text** dialog box (on the **Home** tab, click the **Font** arrow).</span></span> 
  
<span data-ttu-id="9db08-113">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LockTextEdit 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="9db08-113">To get a reference to the LockTextEdit cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9db08-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="9db08-114">Cell name:</span></span>  <br/> | <span data-ttu-id="9db08-115">LockTextEdit</span><span class="sxs-lookup"><span data-stu-id="9db08-115">LockTextEdit</span></span>  <br/> |
   
<span data-ttu-id="9db08-116">若要从某个程序按索引获取对 LockTextEdit 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="9db08-116">To get a reference to the LockTextEdit cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9db08-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="9db08-117">Section index:</span></span>  <br/> |<span data-ttu-id="9db08-118">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="9db08-118">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="9db08-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="9db08-119">Row index:</span></span>  <br/> |<span data-ttu-id="9db08-120">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="9db08-120">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="9db08-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="9db08-121">Cell index:</span></span>  <br/> |<span data-ttu-id="9db08-122">**visLockTextEdit**</span><span class="sxs-lookup"><span data-stu-id="9db08-122">**visLockTextEdit**</span></span> <br/> |
   

