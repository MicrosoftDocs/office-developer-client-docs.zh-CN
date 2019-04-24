---
title: Format 函数（Access 自定义 Web 应用）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
ms.assetid: 550fc235-f0b9-4d8e-805b-ce467821a8c9
description: 返回根据指定的模式进行格式化的值。
localization_priority: Priority
ms.openlocfilehash: 5331df30f276a7edd0571e9bf24c759d57ec6a54
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308202"
---
# <a name="format-function-access-custom-web-app"></a><span data-ttu-id="f75b5-103">Format 函数（Access 自定义 Web 应用）</span><span class="sxs-lookup"><span data-stu-id="f75b5-103">Format Function (Access custom web app)</span></span>

<span data-ttu-id="f75b5-104">返回根据指定的模式进行格式化的值。</span><span class="sxs-lookup"><span data-stu-id="f75b5-104">Returns a value formatted according to a specified pattern.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f75b5-105">本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="f75b5-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="f75b5-106">> 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="f75b5-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="f75b5-107">语法</span><span class="sxs-lookup"><span data-stu-id="f75b5-107">Syntax</span></span>

 <span data-ttu-id="f75b5-108">**Format** (*Expression*, *Format*)</span><span class="sxs-lookup"><span data-stu-id="f75b5-108">**Format** (*Expression*, *Format*)</span></span> 
  
<span data-ttu-id="f75b5-109">**Format** 函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="f75b5-109">The **Format** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="f75b5-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="f75b5-110">**Argument name**</span></span>|<span data-ttu-id="f75b5-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="f75b5-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="f75b5-112">*Expression*</span><span class="sxs-lookup"><span data-stu-id="f75b5-112">*Expression*</span></span>  <br/> |<span data-ttu-id="f75b5-113">要设置格式的受支持数据类型的表达式。</span><span class="sxs-lookup"><span data-stu-id="f75b5-113">Expression of a supported data type to format.</span></span>  <br/> |
| <span data-ttu-id="f75b5-114">*Format*</span><span class="sxs-lookup"><span data-stu-id="f75b5-114">*Format*</span></span>  <br/> | <span data-ttu-id="f75b5-115">格式模式。</span><span class="sxs-lookup"><span data-stu-id="f75b5-115">A format pattern.</span></span> <span data-ttu-id="f75b5-116">格式参数必须包含有效的格式字符串，作为标准格式字符串（例如，“C”或“D”）或日期和数字值的自定义字符的模式（例如，“MMMM dd、yyyy (dddd)”）。</span><span class="sxs-lookup"><span data-stu-id="f75b5-116">The format argument must contain a valid format string, either as a standard format string (for example, "C" or "D"), or as a pattern of custom characters for dates and numeric values (for example, "MMMM dd, yyyy (dddd)").</span></span> <span data-ttu-id="f75b5-117">有关详细信息，请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="f75b5-117">For more information, see Remarks.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f75b5-118">备注</span><span class="sxs-lookup"><span data-stu-id="f75b5-118">Remarks</span></span>

<span data-ttu-id="f75b5-119">对于 *Format* 参数，可以传递与以下任何模式匹配的字符串：</span><span class="sxs-lookup"><span data-stu-id="f75b5-119">For the  *Format*  parameter, you can pass strings that match any of the following patterns:</span></span> 
  
- [<span data-ttu-id="f75b5-120">标准数字格式字符串</span><span class="sxs-lookup"><span data-stu-id="f75b5-120">Standard Numeric Format Strings</span></span>](https://msdn.microsoft.com/library/dwhawy9k%28v=vs.110%29.aspx)
    
- [<span data-ttu-id="f75b5-121">自定义数字格式字符串</span><span class="sxs-lookup"><span data-stu-id="f75b5-121">Custom Numeric Format Strings</span></span>](https://msdn.microsoft.com/library/0c899ak8%28v=vs.110%29.aspx)
    
- [<span data-ttu-id="f75b5-122">标准日期和时间格式字符串</span><span class="sxs-lookup"><span data-stu-id="f75b5-122">Standard Date and Time Format Strings</span></span>](https://msdn.microsoft.com/library/az4se3k1%28v=vs.110%29.aspx)
    
- [<span data-ttu-id="f75b5-123">自定义日期和时间格式字符串</span><span class="sxs-lookup"><span data-stu-id="f75b5-123">Custom Date and Time Format Strings</span></span>](https://msdn.microsoft.com/library/8kb3ddd4%28v=vs.110%29.aspx)
    
<span data-ttu-id="f75b5-124">不能在 Access 2013 Web 应用的以下区域中使用 **Format** 函数：</span><span class="sxs-lookup"><span data-stu-id="f75b5-124">You cannot use the **Format** function in the following areas of Access 2013 web apps:</span></span> 
  
- <span data-ttu-id="f75b5-125">表级别的计算列</span><span class="sxs-lookup"><span data-stu-id="f75b5-125">Calculated columns at the table level</span></span>
    
- <span data-ttu-id="f75b5-126">UI 宏</span><span class="sxs-lookup"><span data-stu-id="f75b5-126">UI macros</span></span>
    
- <span data-ttu-id="f75b5-127">视图中的表达式（例如，在窗体中）</span><span class="sxs-lookup"><span data-stu-id="f75b5-127">Expressions in views (for example, in forms)</span></span>
    

