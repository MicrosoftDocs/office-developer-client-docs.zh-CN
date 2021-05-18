---
title: HYPERLINK 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251441
localization_priority: Normal
ms.assetid: 943636a6-e135-a626-7924-11e238156548
description: 导航到指定的地址，它可以是文件、UNC 或 URL 路径。
ms.openlocfilehash: 5e4952c3d56eff0cb1e6518928a7b8259f645046
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329944"
---
# <a name="hyperlink-function"></a><span data-ttu-id="85093-103">HYPERLINK 函数</span><span class="sxs-lookup"><span data-stu-id="85093-103">HYPERLINK Function</span></span>

<span data-ttu-id="85093-104">导航到指定的地址，它可以是文件、UNC 或 URL 路径。</span><span class="sxs-lookup"><span data-stu-id="85093-104">Navigates to the specified address, which can be a file, UNC, or URL path.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="85093-105">语法</span><span class="sxs-lookup"><span data-stu-id="85093-105">Syntax</span></span>

<span data-ttu-id="85093-106">HYPERLINK (" \*\* *address* \*\* "[，" \*\* *subaddress* \*\* "，" \*\* *extrainfo* \*\* "， \*\* *window* \*\*，" \*\* *frame* \*\* "]) </span><span class="sxs-lookup"><span data-stu-id="85093-106">HYPERLINK(" \*\* *address* \*\* "[," \*\* *subaddress* \*\* "," \*\* *extrainfo* \*\* ", \*\* *window* \*\*," \*\* *frame* \*\* "])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="85093-107">参数</span><span class="sxs-lookup"><span data-stu-id="85093-107">Parameters</span></span>

|<span data-ttu-id="85093-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="85093-108">**Name**</span></span>|<span data-ttu-id="85093-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="85093-109">**Required/Optional**</span></span>|<span data-ttu-id="85093-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="85093-110">**Data Type**</span></span>|<span data-ttu-id="85093-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="85093-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="85093-112">_address_</span><span class="sxs-lookup"><span data-stu-id="85093-112">_address_</span></span> <br/> |<span data-ttu-id="85093-113">必需</span><span class="sxs-lookup"><span data-stu-id="85093-113">Required</span></span>  <br/> |<span data-ttu-id="85093-114">**String**</span><span class="sxs-lookup"><span data-stu-id="85093-114">**String**</span></span> <br/> |<span data-ttu-id="85093-115">完整路径或相对路径。</span><span class="sxs-lookup"><span data-stu-id="85093-115">A full path or a relative path.</span></span>  <br/> |
| <span data-ttu-id="85093-116">_subaddress_</span><span class="sxs-lookup"><span data-stu-id="85093-116">_subaddress_</span></span> <br/> |<span data-ttu-id="85093-117">可选</span><span class="sxs-lookup"><span data-stu-id="85093-117">Optional</span></span>  <br/> |<span data-ttu-id="85093-118">**字符串**</span><span class="sxs-lookup"><span data-stu-id="85093-118">**String**</span></span> <br/> |<span data-ttu-id="85093-p101">指定地址中要链接到的位置。例如，如果地址是一个 Microsoft Visio 文件，则子地址可以是一个页名；如果是一个 Microsoft Excel 文件，则子地址可以是一个工作表或工作表内的某个区域；如果是一个 HTML 页的 URL，则子地址可以是一个定位点。</span><span class="sxs-lookup"><span data-stu-id="85093-p101">Specifies a location within address to link to. For example, if address is a Microsoft Visio file, subaddress can be a page name; if a Microsoft Excel file, subaddress can be a worksheet or range within a worksheet; if a URL for an HTML page, subaddress can be an anchor.</span></span>  <br/> |
| <span data-ttu-id="85093-121">_extrainfo_</span><span class="sxs-lookup"><span data-stu-id="85093-121">_extrainfo_</span></span> <br/> |<span data-ttu-id="85093-122">可选</span><span class="sxs-lookup"><span data-stu-id="85093-122">Optional</span></span>  <br/> |<span data-ttu-id="85093-123">**字符串**</span><span class="sxs-lookup"><span data-stu-id="85093-123">**String**</span></span> <br/> |<span data-ttu-id="85093-124">传递用于解析 URL 的信息，如图像映射的坐标。</span><span class="sxs-lookup"><span data-stu-id="85093-124">Passes information used in resolving the URL, such as the coordinates of an image map.</span></span>  <br/> |
| <span data-ttu-id="85093-125">_window_</span><span class="sxs-lookup"><span data-stu-id="85093-125">_window_</span></span> <br/> |<span data-ttu-id="85093-126">可选</span><span class="sxs-lookup"><span data-stu-id="85093-126">Optional</span></span>  <br/> |<span data-ttu-id="85093-127">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="85093-127">**Boolean**</span></span> <br/> |<span data-ttu-id="85093-p102">指定是否在新窗口中打开超链接。默认值为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="85093-p102">Specifies whether the hyperlink is opened in a new window. The default value is FALSE.</span></span>  <br/> |
| <span data-ttu-id="85093-130">_frame_</span><span class="sxs-lookup"><span data-stu-id="85093-130">_frame_</span></span> <br/> |<span data-ttu-id="85093-131">可选</span><span class="sxs-lookup"><span data-stu-id="85093-131">Optional</span></span>  <br/> |<span data-ttu-id="85093-132">**字符串**</span><span class="sxs-lookup"><span data-stu-id="85093-132">**String**</span></span> <br/> | <span data-ttu-id="85093-p103">指定当 Visio 作为 ActiveX 浏览器（如 Microsoft Internet Explorer 3.0 或更高版本）中的活动文档打开时，它所针对的框架的名称。默认值是一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="85093-p103">Specifies the name of a frame to target when Visio is open as an Active document in an ActiveX browser, such as Microsoft Internet Explorer 3.0 or later. The default is an empty string.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="85093-135">备注</span><span class="sxs-lookup"><span data-stu-id="85093-135">Remarks</span></span>

<span data-ttu-id="85093-p104">如果文档没有基础路径，则 Visio 将按照文档路径导航。如果文档尚未保存，则超链接为未定义。</span><span class="sxs-lookup"><span data-stu-id="85093-p104">If the document has no base path, Visio navigates according to the document path. If the document has not been saved, the hyperlink is undefined.</span></span> 
  
<span data-ttu-id="85093-138">相对路径基于 **“Visio 属性”** 对话框中指定的 **“超链接基础”** 域。</span><span class="sxs-lookup"><span data-stu-id="85093-138">Relative paths are based on the **Hyperlink base** field specified in the **Visio Properties** dialog box.</span></span> 
  
<span data-ttu-id="85093-139">您可以使用 GOTOPAGE 函数来导航文档页。</span><span class="sxs-lookup"><span data-stu-id="85093-139">You can use the GOTOPAGE function to navigate to pages of a document.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="85093-140">示例 1</span><span class="sxs-lookup"><span data-stu-id="85093-140">Example 1</span></span>

 `HYPERLINK("C:\My Documents\Drawing1.vsdx")`
  
## <a name="example-2"></a><span data-ttu-id="85093-141">示例 2</span><span class="sxs-lookup"><span data-stu-id="85093-141">Example 2</span></span>

 `HYPERLINK("\\Server\Share\Drawing1.vsdx")`
  
## <a name="example-3"></a><span data-ttu-id="85093-142">示例 3</span><span class="sxs-lookup"><span data-stu-id="85093-142">Example 3</span></span>

 `HYPERLINK("https://www.microsoft.com")`
  
## <a name="example-4"></a><span data-ttu-id="85093-143">示例 4</span><span class="sxs-lookup"><span data-stu-id="85093-143">Example 4</span></span>

 `HYPERLINK("..\data.xlsx","sheet1!A1")`
  

