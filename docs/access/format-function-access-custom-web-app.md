---
title: Format 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 550fc235-f0b9-4d8e-805b-ce467821a8c9
description: 返回一个值，根据指定的模式设置格式。
ms.openlocfilehash: 974b56ab8e6bc3f97c1931ba67ca9cd08c3511c9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773468"
---
# <a name="format-function-access-custom-web-app"></a><span data-ttu-id="fed80-103">Format 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="fed80-103">Format Function (Access custom web app)</span></span>

<span data-ttu-id="fed80-104">返回一个值，根据指定的模式设置格式。</span><span class="sxs-lookup"><span data-stu-id="fed80-104">Returns a value formatted according to a specified pattern.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fed80-105">本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="fed80-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="fed80-106">> 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="fed80-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="fed80-107">语法</span><span class="sxs-lookup"><span data-stu-id="fed80-107">Syntax</span></span>

 <span data-ttu-id="fed80-108">**格式**（*表达式*，*格式*）</span><span class="sxs-lookup"><span data-stu-id="fed80-108">**Format** (*Expression*, *Format*)</span></span> 
  
<span data-ttu-id="fed80-109">**Format**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="fed80-109">The **Format** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="fed80-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="fed80-110">**Argument name**</span></span>|<span data-ttu-id="fed80-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="fed80-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="fed80-112">*Expression*</span><span class="sxs-lookup"><span data-stu-id="fed80-112">*Expression*</span></span>  <br/> |<span data-ttu-id="fed80-113">要设置格式的支持的数据类型的表达式。</span><span class="sxs-lookup"><span data-stu-id="fed80-113">Expression of a supported data type to format.</span></span>  <br/> |
| <span data-ttu-id="fed80-114">*Format*</span><span class="sxs-lookup"><span data-stu-id="fed80-114">*Format*</span></span>  <br/> | <span data-ttu-id="fed80-115">格式图案。</span><span class="sxs-lookup"><span data-stu-id="fed80-115">A format pattern.</span></span> <span data-ttu-id="fed80-116">Format 参数必须包含有效格式字符串，作为标准格式字符串 （例如，"C"或"D"） 或自定义字符的模式的日期和数字值 (例如，"MMMM dd，yyyy (dddd)")。</span><span class="sxs-lookup"><span data-stu-id="fed80-116">The format argument must contain a valid format string, either as a standard format string (for example, "C" or "D"), or as a pattern of custom characters for dates and numeric values (for example, "MMMM dd, yyyy (dddd)").</span></span> <span data-ttu-id="fed80-117">有关详细信息，请参阅备注。</span><span class="sxs-lookup"><span data-stu-id="fed80-117">For more information, see Remarks.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fed80-118">说明</span><span class="sxs-lookup"><span data-stu-id="fed80-118">Remarks</span></span>

<span data-ttu-id="fed80-119">对于*格式*参数，则可以传递与任何以下模式匹配的字符串：</span><span class="sxs-lookup"><span data-stu-id="fed80-119">For the  *Format*  parameter, you can pass strings that match any of the following patterns:</span></span> 
  
- [<span data-ttu-id="fed80-120">标准数字格式字符串</span><span class="sxs-lookup"><span data-stu-id="fed80-120">Standard Numeric Format Strings</span></span>](http://msdn.microsoft.com/en-us/library/dwhawy9k%28v=vs.110%29.aspx)
    
- [<span data-ttu-id="fed80-121">自定义数字格式字符串</span><span class="sxs-lookup"><span data-stu-id="fed80-121">Custom Numeric Format Strings</span></span>](http://msdn.microsoft.com/en-us/library/0c899ak8%28v=vs.110%29.aspx)
    
- [<span data-ttu-id="fed80-122">标准的日期和时间格式字符串</span><span class="sxs-lookup"><span data-stu-id="fed80-122">Standard Date and Time Format Strings</span></span>](http://msdn.microsoft.com/en-us/library/az4se3k1%28v=vs.110%29.aspx)
    
- [<span data-ttu-id="fed80-123">自定义日期和时间格式字符串</span><span class="sxs-lookup"><span data-stu-id="fed80-123">Custom Date and Time Format Strings</span></span>](http://msdn.microsoft.com/en-us/library/8kb3ddd4%28v=vs.110%29.aspx)
    
<span data-ttu-id="fed80-124">不能使用**Format**函数在 Access 2013 web 应用程序的以下方面：</span><span class="sxs-lookup"><span data-stu-id="fed80-124">You cannot use the **Format** function in the following areas of Access 2013 web apps:</span></span> 
  
- <span data-ttu-id="fed80-125">表级计算的列</span><span class="sxs-lookup"><span data-stu-id="fed80-125">Calculated columns at the table level</span></span>
    
- <span data-ttu-id="fed80-126">UI 宏</span><span class="sxs-lookup"><span data-stu-id="fed80-126">UI macros</span></span>
    
- <span data-ttu-id="fed80-127">视图 （例如，在窗体） 中的表达式</span><span class="sxs-lookup"><span data-stu-id="fed80-127">Expressions in views (for example, in forms)</span></span>
    

