---
title: LOC Function (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251455
localization_priority: Normal
ms.assetid: 7db7a8ed-50a9-8495-b978-42a2fddb466a
description: 获取一个形状的本地坐标中定义的点，并返回以与公式相关联的形状的本地坐标表示的等效点。
ms.openlocfilehash: 196e2c92ea6ab410b6ecca9767b68605e4eb4d30
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780607"
---
# <a name="loc-function-visioshapesheet"></a><span data-ttu-id="13bc7-103">LOC Function (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="13bc7-103">LOC Function (VisioShapeSheet)</span></span>

<span data-ttu-id="13bc7-104">获取一个形状的本地坐标中定义的点，并返回以与公式相关联的形状的本地坐标表示的等效点。</span><span class="sxs-lookup"><span data-stu-id="13bc7-104">Takes a point defined in one shape's local coordinates and returns the equivalent point expressed in the local coordinates of the shape associated with the formula.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="13bc7-105">语法</span><span class="sxs-lookup"><span data-stu-id="13bc7-105">Syntax</span></span>

<span data-ttu-id="13bc7-106">LOC (* **指向** *)</span><span class="sxs-lookup"><span data-stu-id="13bc7-106">LOC(** *point* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="13bc7-107">参数</span><span class="sxs-lookup"><span data-stu-id="13bc7-107">Parameters</span></span>

|<span data-ttu-id="13bc7-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="13bc7-108">**Name**</span></span>|<span data-ttu-id="13bc7-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="13bc7-109">**Required/Optional**</span></span>|<span data-ttu-id="13bc7-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="13bc7-110">**Data Type**</span></span>|<span data-ttu-id="13bc7-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="13bc7-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="13bc7-112">_磅_</span><span class="sxs-lookup"><span data-stu-id="13bc7-112">_point_</span></span> <br/> |<span data-ttu-id="13bc7-113">必需</span><span class="sxs-lookup"><span data-stu-id="13bc7-113">Required</span></span>  <br/> |<span data-ttu-id="13bc7-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="13bc7-114">**String**</span></span> <br/> | <span data-ttu-id="13bc7-115">一个形状的本地坐标中定义的点。</span><span class="sxs-lookup"><span data-stu-id="13bc7-115">A point defined in one shape's local coordinates.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="13bc7-116">返回值</span><span class="sxs-lookup"><span data-stu-id="13bc7-116">Return value</span></span>

<span data-ttu-id="13bc7-117">字符串</span><span class="sxs-lookup"><span data-stu-id="13bc7-117">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="13bc7-118">注解</span><span class="sxs-lookup"><span data-stu-id="13bc7-118">Remarks</span></span>

<span data-ttu-id="13bc7-p101">本地坐标是以形状的选择矩形的左下角为基准测量的。两个形状必须在同一页上。</span><span class="sxs-lookup"><span data-stu-id="13bc7-p101">Local coordinates are measured from the lower-left corner of the shape's selection rectangle. Both shapes must be on the same page.</span></span>
  
## <a name="example"></a><span data-ttu-id="13bc7-121">示例</span><span class="sxs-lookup"><span data-stu-id="13bc7-121">Example</span></span>

<span data-ttu-id="13bc7-122">LOC (PNT (Sheet.5 ！LocPinX，Sheet.5 ！LocPinY))</span><span class="sxs-lookup"><span data-stu-id="13bc7-122">LOC(PNT(Sheet.5!LocPinX, Sheet.5!LocPinY))</span></span> 
  
<span data-ttu-id="13bc7-p102">在此表达式中，PNT 将 Sheet.5 中的一组本地坐标转换为一个点。（Sheet.5 是同一绘图页上的另一个形状。）然后，LOC 相对于当前形状的选择矩形的左下角，将这个点转换为当前形状的本地坐标系中的等效点。</span><span class="sxs-lookup"><span data-stu-id="13bc7-p102">In this expression, PNT converts a set of local coordinates in Sheet.5 to a point. (Sheet.5 is another shape on the same drawing page.) LOC then converts that point to an equivalent point in the current shape's local coordinate system, relative to the lower-left corner of the selection rectangle of the current shape.</span></span> 
  
<span data-ttu-id="13bc7-125">Sheet.5 中的 5 是形状的 ID 号，它显示在 **“形状名”** 对话框（**“开发工具”** 选项卡）中。</span><span class="sxs-lookup"><span data-stu-id="13bc7-125">The 5 in Sheet.5 is the ID number for the shape, which is displayed in the **Shape Name** dialog box (**Developer** tab).</span></span> 
  

